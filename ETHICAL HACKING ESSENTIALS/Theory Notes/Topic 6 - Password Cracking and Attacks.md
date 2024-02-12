# Password Hacking 
- What is password 
# Table of Contents

- [Password Hacking](#password-hacking)
- [Table of Contents](#table-of-contents)
- [What is a Password?](#what-is-a-password)
  - [Why as password must not be written down?](#why-as-password-must-not-be-written-down)
  - [Password Complexity](#password-complexity)
- [Example of a good password](#example-of-a-good-password)
- [Password Cracking](#password-cracking)
  - [Password Attacks (Brute Force Attacks)](#password-attacks-brute-force-attacks)
    - [Advantages of Brute Force Attacks](#advantages-of-brute-force-attacks)
    - [Disadvantages of Brute Force Attacks](#disadvantages-of-brute-force-attacks)
  - [Dictionary Attacks](#dictionary-attacks)
  - [Rainbow Table Attacks (Rainbow Cracking) (Which is the most effective and efficient way to crack passwords)](#rainbow-table-attacks-rainbow-cracking-which-is-the-most-effective-and-efficient-way-to-crack-passwords)
  - [Password Guessing](#password-guessing)
  - [Default Passwords](#default-passwords)
- [Password Defenses](#password-defenses)
  - [Salting](#salting)
  - [Password Policies](#password-policies)
- [Linux Password Cracking](#linux-password-cracking)

--- 

# What is a Password?

- A password is a secret word or string of characters that is used for authentication, to prove identity or gain access to a resource
- The most common use of passwords for logical access control
- Sometimes referred to as a logical token
- A secret combination of characters and numbers that only the user should know
## Why as password must not be written down?
- If a password is written down, it can be easily stolen or lost, and the security of the system is compromised
  - Example of this would be a sticky note with a password on it and a user throws it away in the trash
    - An attacker could find the sticky note through dumpster diving and use the password to gain access to the system
  - Another example would be a user writing down their password in a notebook and losing the notebook
    - An attacker could find the notebook and use the password to gain access to the system

## Password Complexity
- A password should be complex enough to prevent unauthorized access
- A complex password is one that is difficult to guess or crack
- A complex password should be at least 8 characters long and contain a combination of uppercase and lowercase letters, numbers, and special characters
- A complex password should not contain any words that can be found in a dictionary, personal information, or easily guessable information


# Example of a good password
|Myth |Explanation|
|---|---|
P4T9#6o is a better password then this_is_a_very_long_password | Even though the first password is a combination of letters, numbers, and special characters, it is still a weak password because it is easily guessable. The second password is a better password because it is long and contains a combination of uppercase and lowercase letters, numbers, and special characters. It is also not easily guessable.|
|The best length for a password is 8 characters | The best length for a password is 15 characters or more. The longer the password, the more secure it is.|
|Replacing letters with numbers, such as J0hn_Sm1th is good |Password-cracking programs can easily look for common words like (John) as well as variations of those words, such as replacing the letter O with the number 0. This makes the password easier to crack.|
|Password cannot include spaces | Passwords can include spaces. In fact, spaces can make a password more secure.|

# Password Cracking

![img](https://i.imgur.com/U9wH3Jg.png)

- Password cracking are techniques used to recover passwords from data that has been stored in or transmitted by a computer system
- Attackers use these techniques to gain unauthorized access to a system
- Most of the time these techniques can be successful because users tend to use weak passwords, reuse passwords, or store passwords in an insecure manner

## Password Attacks (Brute Force Attacks)
- To use every possible combination of letters, numbers, and symbols to crack a password
    - Example of this would be (a-z, A-Z, 0-9, and special characters)

### Advantages of Brute Force Attacks
- Can be successful
- Can be automated
- Can be used to crack any password
- Can be used to crack any encryption
- Can be used to crack any hash
- Can be used to crack any authentication system
- Can be used to crack any system
- Can be used to crack any network
- Can be used to crack any application

### Disadvantages of Brute Force Attacks
- Can be time-consuming
- Can be resource-intensive
    -  Example of this would be a brute force attack on a password that is 15 characters long
        - It would take a long time to crack the password
- Can be noisy
  - For example, if an attacker is trying to crack a password on a network, the network administrator might notice the attack and take action to stop it
- Can be detected
  - IDS/IPS can detect brute force attacks
- Can be blocked
  - Fail2Ban is a popular tool that can be used to block brute force attacks
- Can be prevented
- Can be illegal
- Can be unethical

## Dictionary Attacks
- A dictionary attack is a technique used to crack a password by using a list of words from a dictionary'
- And comparing those hashed dictionary words to those stolen Passwords
- Methods to improve success rate   
  - Use serveral different dictionaries, such as technical or foreign language dictionaries, which increate the number of possible passwords
  - Use of string manipulation along with the dictionary (eg. if the dictionary word is "password", string manipulationcreates anagrams like "drowssap" or "x@xxxxxx" among others)
    - Exmplaination: String manipulation is the process of changing the structure of a string. This can be done by changing the case of the letters, reversing the letters, or replacing the letters with numbers or special characters



![img](https://i.imgur.com/x6MGwK9.png)
## Rainbow Table Attacks (Rainbow Cracking) (Which is the most effective and efficient way to crack passwords)

- What is a Rainbow Table Attacks?
  - A rainbow table attack is a technique used to crack a password by using a precomputed table of hashes
  - The table contains a list of hashes and their corresponding plaintext passwords
  - Each hash in the table is unique
  - Example of this:
    - If an attacker has a stolen password hash, the attacker can use the rainbow table to look up the hash and find the corresponding plaintext password
    - The attacker can then use the plaintext password to gain access to the system
    - Example of this table is shown below

|Hash|Plaintext Password|
|---|---|
|5f4dcc3b5aa765d61d8327deb882cf99|password|
|25d55ad283aa400af464c76d713c07ad|123456|
|098f6bcd4621d373cade4e832627b4f6|test|
|e10adc3949ba59abbe56e057f20f883e|123456|

- Making passwords easier to crack by creating a large pre-generated data set of hashes from nearly every possible password combination

- Generating a rainbow table is a time-consuming process, but once the table is generated, it can be used to crack passwords quickly. 

    - Some rainbow tables can be as large as 160 GB
  - Example of this would be a rainbow table that contains hashes for every possible 8-character password
    - The table would contain 6,634,204,312,890,625 hashes
    - The table would be 160 GB in size


- Rainbow Table Advantages 
  - Can be used repeatedly for attacks on other passwords
  - Rainbow Tables are more efficient than brute force attacks, dictionary attacks, and other password-cracking techniques
  - The amount of Memory and CPU power required to crack a password is less than that of a brute force attack


## Password Guessing
- Password guessing is a technique used to crack a password by guessing the password, based on the attacker's knowledge of the victim
  - Example of this would be an attacker guessing a victim's password based on the victim's name, date of birth, or other personal information
  - There is also leak passwords from other websites that can be used to guess passwords, and some of them work because people tend to reuse passwords


- Steps of Password Guessing
  - The attacker gathers information about the victim
  - The attacker uses the information to guess the victim's password
  - The attacker uses the guessed password to gain access to the system

The Success rate for this method is **very low** but it is still used because it is easy to do and requires no technical skills


## Default Passwords
- These passwords are usually set by the manufacturer of the device, to allow the user to access the device for the first time
- The default password is usually a weak password, and it is often the same for all devices of the same type, some of them also doesn't change after the first login
- This can be used to gain unauthorized access to the device, if a user does not change the default password

 The success rate for this method is **very low** but it is still used because it is easy to do and requires no technical skills

 - Some online tools to search default password:
 - https://open-sez.me
 - https://www.fortypoundhead.com
 - https://cirt.net
 - http://www.defaultpassword.us
 - https://www.routerpasswords.com
-  https://default-password.info
-  https://192-168-1-1ip.mobi
 


 # Password Defenses
 A defence against breaking encrypted passwords with 
 
 ## Salting
 - Use a salt. A salt is a random value that is added to the password before it is hashed. The salt is stored with the hash, and it is used to make the hash unique. This makes it difficult for an attacker to use a rainbow table to crack the password.

   -   These random bits are known as salt

- These make brute force, dictionary, and rainbow table attacks more difficult


``` 
Hashing Algorithms. A hashing algorithm is a mathematical function that takes an input and produces a fixed-size string of characters. The input can be any length, but the output is always the same length. Hashing algorithms are used to convert plaintext passwords into hashes. The hash is then stored in a database. When a user logs in, the password is hashed and compared to the stored hash. If the hashes match, the user is authenticated. If the hashes do not match, the user is not authenticated. The most common hashing algorithms are MD5, SHA-1, and SHA-256. MD5 and SHA-1 are considered weak because they are vulnerable to collision attacks. SHA-256 is considered strong because it is resistant to collision attacks.
```

  ## Password Policies
  - A strong password policy can help prevent unauthorized access to a system
  - The first password policy is to require users to create complex passwords
- Example of a strong password policy
  - 12 characters long
  - One uppercase letter
  - One lowercase letter
  - One number
  - One special character
  - No dictionary words
  - No personal information
- The second password policy is to require users to change their passwords regularly, every 30, 60, or 90 days
- A third password policy is to require users to use different passwords for different systems
- A fourth password policy is to require users to use a password manager
- A fifth password policy is to require users to use multi-factor authentication
- A sixth password policy is to require users to use biometric authentication
- A seventh password policy is to require users to use a passphrase

# Linux Password Cracking
- Linux Passwords are usually hashed and stored in the /etc/shadow file
- The /etc/shadow file is readable only by the root user
  - But an attacker can still gain access to the file by using a privilege escalation attack or using John the Ripper
    - John the Ripper is a popular password-cracking tool that can be used to crack Linux passwords

