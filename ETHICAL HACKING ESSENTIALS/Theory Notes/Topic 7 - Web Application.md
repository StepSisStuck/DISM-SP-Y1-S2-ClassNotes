# Topic 7 - Web Application

# Table of Contents
- [Topic 7 - Web Application](#topic-7---web-application)
- [Table of Contents](#table-of-contents)
- [Web Sites Vulnerabilities](#web-sites-vulnerabilities)
- [Sample Valunerable Web Application](#sample-valunerable-web-application)
- [Cross Cross-Site Scripting (XSS)](#cross-cross-site-scripting-xss)
  - [Stored XSS](#stored-xss)
  - [XSS Attack on MySpace](#xss-attack-on-myspace)
    - [Some ways to prevent XSS](#some-ways-to-prevent-xss)
    - [Some ways to mitigate XSS Vulnerabilities](#some-ways-to-mitigate-xss-vulnerabilities)
- [Cross-Site Request Forgery (CSRF)](#cross-site-request-forgery-csrf)
  - [CSRF Attack](#csrf-attack)
  - [Some ways to prevent CSRF](#some-ways-to-prevent-csrf)
- [Mitigating  Vulnerabilities](#mitigating--vulnerabilities)
- [SQL Injection](#sql-injection)
  - [Take a step back, what is SQL?](#take-a-step-back-what-is-sql)
  - [Simple SQL Injection](#simple-sql-injection)
    - [SQL Injection Techniques](#sql-injection-techniques)
  - [SQL Error Message](#sql-error-message)
  - [Finding out table columns](#finding-out-table-columns)
  - [Meta infomation](#meta-infomation)
  - [SQL Injection Injection](#sql-injection-injection)
  - [Finding out Column Names](#finding-out-column-names)
  - [Ways to Mitigate SQL Injection](#ways-to-mitigate-sql-injection)
    - [Database Login](#database-login)
    - [Fixing the Vulnerability](#fixing-the-vulnerability)
- [Data Tampering](#data-tampering)
- [Form Data](#form-data)
  - [Hidden Field](#hidden-field)
- [Cookies Values](#cookies-values)
- [Session Hijacking](#session-hijacking)
  - [Fixing Web Application Vulnerabilities](#fixing-web-application-vulnerabilities)
- [Error Messages](#error-messages)
  - [Fixing the Vulnerability](#fixing-the-vulnerability-1)


---
# Web Sites Vulnerabilities
- Web Application security is more important than ever.
- OWASP (Open Web Application Security Project) is a worldwide not-for-profit charitable organization focused on improving the security of software, and here is their top 10 vulnerabilities:
    - Cross-Site Scripting (XSS)
      - XSS is a client-side code injection attack. The attacker aims to execute malicious scripts in a web browser of the victim by including malicious code in a legitimate web page or web application, how it works:
        - The attacker finds a way to inject malicious scripts into web pages viewed by other users.
        - The attacker sends a link to the victim.
        - The victim clicks the link and the malicious script is executed.
    - Forcefuk Browsing
      - Forceful browsing is an attack where the attacker tries to access files and directories that are not meant to be accessed by the user. The attacker tries to access files and directories by manipulating the URL.
      - Example: Actual Website: http://example.com/user-welcome  
      - Attacker change it to: http://www.example.com/admin
        - The attacker tries to access the admin page by manipulating the URL. 
    - Parameter Tampering, cookie poisoning, and hidden field manipulation
      - Parameter tampering is an attack where the attacker tries to modify parameters of a URL or form. The attacker tries to modify parameters to gain unauthorized access to the web application.
      - Example: Actual URL: http://example.com/user-welcome?user=admin
      - Attacker change it to: http://example.com/user-welcome?user=admin&role=admin
        - The attacker tries to modify the role parameter to gain unauthorized access to the web application.
      - Cookie poisoning is an attack where the attacker tries to modify the content of a cookie. The attacker tries to modify the content of a cookie to gain unauthorized access to the web application.
      - Hidden field manipulation is an attack where the attacker tries to modify the content of a hidden field. The attacker tries to modify the content of a hidden field to gain unauthorized access to the web application.
  - SQL Injection
    - SQL injection is a code injection technique that might destroy your database. SQL injection is one of the most common web hacking techniques.
    - SQL injection is the placement of malicious code in SQL statements, via web page input.
    - SQL injection usually occurs when you ask a user for input, like their username/userid, and instead of a name/id, the user gives you an SQL statement that you will unknowingly run on your database.
    - Example: 
      - SELECT * FROM Users WHERE Name = 'admin' AND Password = 'admin'
      - If the user input is: admin' OR '1'='1
      - The SQL statement will become: SELECT * FROM Users WHERE Name = 'admin' OR '1'='1' AND Password = 'admin'
      - The SQL statement will return all the rows from the Users table, because '1'='1' is always true.

# Sample Valunerable Web Application
- There are many sample web applications created with valunerabilities for learning purposes 
- One of the most popular is DVWA (Damn Vulnerable Web Application)
  - DVWA is a PHP/MySQL web application that is damn vulnerable. Its main goals are to be an aid for security professionals to test their skills and tools in a legal environment, help web developers better understand the processes of securing web applications and aid teachers/students to teach/learn web application security in a classroom environment.
# Cross Cross-Site Scripting (XSS)
- They can occur when the website takes information from a user and displays it without validating the input.
- The attacker can use this vulnerability to inject malicious scripts into web pages viewed by other users which can generate a unexpected output
- The attacker can use this vulnerability to steal information from the user, such as cookies, session tokens, or other sensitive information.
  - Example of this:
  ![img](https://i.imgur.com/jBGKZQE.png)
  (Some newer browsers have built-in protection against this type of attack)
  
  They Relies on the ability of the web application to trust the user input and display it without validation.
  
- Besides Creating a pop-up window, XSS can be used to : 
  - Deface a website
  - Redirect the user to another website
  - Manmipulate the content of the website
  - Any function: windows.alert(), read/write files, etc.
  - "Poison" Cookies
  - And many more...
  

## Stored XSS
- Stored XSS happens when the malicious script is stored in the web application's database and is displayed to the user when the user visits the affected page.
- The attacker's crafted data is stored in the database and is displayed to the user when the user visits the affected page.
- Example of this:
  - The attacker enter malicious input into a review or comments textarea. Other web visitors who visits the Review or Comments page will be affected by the malicious script.

## XSS Attack on MySpace

- http://www.caughq.org/advisories/CAU-2006-0001.txt 
- The attacker submitted CSS (Cascading Style Sheets) code in his profile page in MySpace which prevented the normal navigation menu from displaying.
- Hacker created his own navigation menu, which has a login page that looks like the original MySpace login page.
- Users who visited the attacker's profile page were tricked into entering their login credentials into the attacker's fake login page.
- The attacker was able to steal the login credentials of the users who visited his profile page.

### Some ways to prevent XSS
- Here are some
  - Input Validation
  - Output Encoding
  - Content Security Policy (CSP)
  - HTTPOnly Cookie
  - Secure Flag
  - X-Content-Type-Options

- Look out for some codes that takes input directly from user and post it back into the webpage 
- Perform data sanitization
        
         E.g Encode with '<' and '>' with '&lt;' and '&gt;'
- Advanced XSS can escape simple encoding checks for allowable chraracters instead
    - Use more stringent control: Explicitly check for allowable chracaters instead

### Some ways to mitigate XSS Vulnerabilities

- Most Languages like PHP, ASP.NET, Java, etc. have built-in functions to prevent XSS attacks.
        
        & becomes &amp;   
        < becomes &lt;
        > becomes &gt;
        " becomes &quot;

https://www.owasp.org/index.php Top_10-2017_A7-Cross-Site_Scripting_(XSS)

This helps to prevent the browser from interpreting the input as HTML or JavaScript.

# Cross-Site Request Forgery (CSRF)
- CSRF is an attack that tricks the victim into submitting a malicious request. It inherits the identity and privileges of the victim to perform an undesired function on their behalf.

- Example of this
    - User have logged into a bank website and is browsing the web
    - Usually the user would have multiple tabs open and they are also browsing other websites
    - If he encounters a malicious website with CSRF, the malicious website can send a request to the bank website to transfer money from the user's account to the attacker's account.

## CSRF Attack
- Because the user is already authenticated, the attacker and cause transactions to be made on behalf of the user without the user's knowledge.
- The website thinks that the request is coming from the user, and the user is already authenticated, so the website will process the request.

## Some ways to prevent CSRF
- Here are some
  - Use of Anti-CSRF Tokens
  - SameSite Cookie Attribute
  - Referrer Policy
  - Double Submit Cookie
  - Synchronizer Token Pattern
  - Origin Header
  - Custom Request Headers
  - Content Security Policy (CSP)

- Besides authentication, the server should also verify that the request is coming from the same origin as the website.
  - Send some challenge token/data associated with the current user's session with the request 
  - Re-authenticate the user for sensitive operations (e.g. one-time password)
  - Use of CAPTCHA for sensitive operations
- When performing sensitive operations, eg. changing password, transferring money, etc, don't open other tabs or browse other websites.

# Mitigating  Vulnerabilities
- Parse the parameters if they are being used to access files 
  - Remove any '/' or '\' characters

- Avoid common names for admin pages like admin.php, admin.html, etc.
- Restrict access to admin pages to only authorized users
- Expire sessions variables after a certain period of inactivity

# SQL Injection
- Fun fact about SQL Injection
  - SQL injection is a code injection technique that might destroy your database. SQL injection is one of the most common web hacking techniques.
  - Most common web application interacts with database to persistaently store data
  - Connection to the database requires login credentials to be presented during the connection
  - Interface to the database is usually done through "queries" which are written in SQL (Structured Query Language)


- What does SQL Injecion do?
  - SQL injection is the placement of malicious code in SQL statements, via web page input.
  - SQL injection usually occurs when you ask a user for input, like their username/userid, and instead of a name/id, the user gives you an SQL statement that you will unknowingly run on your database.
  - Example: 
    - SELECT * FROM Users WHERE Name = 'admin' AND Password = 'admin'
    - If the user input is: admin' OR '1'='1
    - The SQL statement will become: SELECT * FROM Users WHERE Name = 'admin' OR '1'='1' AND Password = 'admin'
    - The SQL statement will return all the rows from the Users table, because '1'='1' is always true.

- Consider the following VB codes:
```vb
query1 = "SELECT user, password FROM users WHERE user = '" & Request.Form("username") & "' AND password = '" & Request.Form("password") & "'"
```
 - Programmers may assume user will always key in username and password 
 - SQL injection - Techniques where attackers manipulate the input data so as to execute query other than what is intended


## Take a step back, what is SQL?
- SQL is a standard language for storing, manipulating and retrieving data in databases.
- SQL is used to query, insert, update and modify data.
- SQL is used to perform many operations on the database, such as updating records, deleting records, creating new tables, etc.
- They can be used in many different database systems, such as MySQL, SQL Server, Access, Oracle, Sybase, Informix, etc.
  - They store data in tables, and the tables are related to each other, so that the database can be queried and the data can be retrieved in a meaningful way. 
    - Example would be an company have a customer table, and an order table. The customer table is related to the order table, so that the company can query the database to find out what orders a customer has made.
## Simple SQL Injection
- Simple Injection is the most common type of SQL injection. It occurs when the attacker uses the input fields to inject the malicious SQL code.
- They can be done with a ' or 1=1 -- '
  - Select * from users where username = ' ' or 1=1 -- ' and password = ' '
  - Always true, so it will return all the rows from the users table
  - If used for login processing, the first record being returned will be used to authenticate the user


### SQL Injection Techniques

- They can cause and error or return all the rows from the table
- Error messages can reveal information about the database
- These data can be used to further exploit the database

## SQL Error Message
- Inject Quotes such as ' " reveal details of query
- Eg. We know that now **hash** has a column name for the password 

![img](https://i.imgur.com/cxpsPsZ.png)

  

## Finding out table columns
- SQL injection requires creativity 
- The attacker needs to find out the table names and column names in the database


## Meta infomation

Most Database Management Systems (DBMS) have a special table called "information_schema" which contains meta-information about the database such as the table names, column names, data types, etc.

- Example of this:
  - SQL Server and MySQL(version 5.0 and above) SQL Standard (ISO/IEC 9075) Information_Schema.tables


## SQL Injection Injection 
- Using UNION to find out tables names and column names
- ' untion select table_name from information_schema.tables --

- Number of columns in UNION must be the same as the number of columns in the original query
  
- Take a step back, what is UNION?
  - The UNION operator is used to combine the result-set of two or more SELECT statements.
  - Each SELECT statement within the UNION must have the same number of columns in the result sets with similar data types.

Cycle through entire table names

’ union select table_name from information_schema.tables where table_name NOT in (‘CHARACTER_SETS’) --

## Finding out Column Names
- Using same methods as finding out table names
- ' union select column_name from information_schema.columns where table_name=‘user’ --

## Ways to Mitigate SQL Injection
- Here are some
  - Use of Prepared Statements
  - Use of Stored Procedures
  - Use of ORM (Object-Relational Mapping)
  - Use of Parameterized Queries
  - Use of White List Input Validation
  - Use of Web Application Firewall (WAF)
  - Use of Input Validation
  - Use of Output Encoding
  - Use of Content Security Policy (CSP)
  - Use of HTTPOnly Cookie
  - Use of Secure Flag
  - Use of X-Content-Type-Options
  - Use of X-Frame-Options
  - Use of X-XSS-Protection
  - Use of SameSite Cookie Attribute
  - Use of Referrer Policy
  - Use of Double Submit Cookie
  - Use of Synchronizer Token Pattern
  - Use of Origin Header
  - Use of Custom Request Headers

- Limit database privileges for the web application to only the necessary privileges
- Use prepared statements or stored procedures (these are not vulnerable to SQL injection)

### Database Login
- Hard coding of login credentials in the application code is a bad practice
  - Example of this code
```vb
dbconn = MySQLdb.connect(db="sales", user= "sa",passwd="secret",database="sales")
```
- They are difficult to change and manage
- Different credentials for different environments (development, testing, production)
- Leaking of credentials if the code is shared or published

### Fixing the Vulnerability
- Use of configuration files
  - Store the credentials in a configuration file
- Use Hardware Security Modules (HSM)
  - Store the credentials in a HSM
  - Also known as Crpto Box
  - Keys are kept within the HSM and never leave the HSM
- Limit the privileges of the database user
  - Use the principle of least privilege
  - Only grant the necessary privileges to the database user
- Restrict client access to the database
  - Use of firewalls to restrict access to the database
  - Use of VPN to connect to the database

# Data Tampering
- There are a lot of infomation being carried by HTTP messages
  - Cookies Values
  - Form Field
  - Query String
  - HTTP Headers
- Undesirable changes to data before it is sent to the server or before it is received by the client

# Form Data 
- Form data can be tampered with before it is sent to the server
- Most Developers uses client-side validation to validate the form data like JavaScript
- Validation can be bypassed easily thru direct manipulation of the form data

## Hidden Field
- Hidden fields are used to store data that should not be visible to the user
- BUT THEY ARE NOT REALLY HIDDEN
- They can be easily manipulated by the user
![img](https://i.imgur.com/wRYOwcy.png)

# Cookies Values 
- A common way to store user information is to use cookies
- Essential stored in a text file on the user's computer
- Can be tricked to write cookies of another domain (eg. Using XSS)
  
# Session Hijacking
- Session hijacking is the act of taking control of a user session after successfully obtaining or generating an authentication session ID
- Exploits the XSS vulnerability in the application
- Victim's session ID is stolen and used by the attacker to impersonate the victim
- XSS page send session ID to the attacker's server
- Attacker logs to the system and replaces his session ID with the victim's session ID

## Fixing Web Application Vulnerabilities
- Do not trust user input
- Cookies should not be used entirely for authentication
- Use HTTP_REFERER to check if the request is coming from the same domain
- Use USER_AGENT to check if the request is coming from the same browser
- Use of CAPTCHA for sensitive operations
- HTTPS or SSL/TLS should be used to encrypt the data transmitted between the client and the server

# Error Messages 
- Application needs to responds to error
- Some Error are made by user and can be corrected by users
  - Application needs to inform users about error
  - Errors messages needs to be informative and helpful
- Some errors are made by the application
  - Application needs to log the error
  - Application needs to inform the user about the error
  - Application needs to inform the administrator about the error


This messages reveals information about the type of database and the version of the database
![img](https://i.imgur.com/sNTYPeJ.png)


![img](https://i.imgur.com/sgT4Zyt.png)

## Fixing the Vulnerability
- Application codes should not reveal any information about the database
  - They should only show functional error messages
  - Error handling should be done in the application code
  - The Admin should only know the error messages
    - Example of this code list 

| Error Code | Error Message |
|------------|---------------|
| 404        | Page Not Found|
| 500        | Internal Server Error|
| 403        | Forbidden|
| 401        | Unauthorized|
| 400        | Bad Request|


- Make sure  they do not reveal any information about the database
- Extensive testing of error handing (most people do functional testing, but not error testing)