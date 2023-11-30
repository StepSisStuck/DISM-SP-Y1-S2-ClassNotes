# Topic 3 - Authentication Credentials


# Table of Contents
- [Topic 3 - Authentication Credentials](#topic-3---authentication-credentials)
- [Table of Contents](#table-of-contents)
- [Types of Authentication Credentials](#types-of-authentication-credentials)
  - [Something you know: Passwords](#something-you-know-passwords)
    - [Attacks on Passwords](#attacks-on-passwords)
    - [Password Spraying](#password-spraying)
    - [Rule Attack](#rule-attack)
    - [Dictionary Attack](#dictionary-attack)
    - [Password Collections](#password-collections)
  - [Smartphone and Security Tokens](#smartphone-and-security-tokens)
    - [Specialized Security Tokens](#specialized-security-tokens)
  - [Biometrics](#biometrics)
    - [Physiological Biomertics](#physiological-biomertics)
  - [Specialized Biometric Devices](#specialized-biometric-devices)
    - [Biometric Disadvantages](#biometric-disadvantages)
  - [Cogiitive Biometrics](#cogiitive-biometrics)
  - [Behavioral Biometrics](#behavioral-biometrics)
- [Authentication Solutions](#authentication-solutions)
- [Password Security](#password-security)
    - [Managing Passwords](#managing-passwords)
    - [Single Sign-On (SSO)](#single-sign-on-sso)
    - [Authentication Services](#authentication-services)
    - [RADUIS](#raduis)
    - [Kerberos](#kerberos)
    - [TACACS (Terminal Access Controller Access Control System)](#tacacs-terminal-access-controller-access-control-system)
    - [Directory Services](#directory-services)
    - [SAML (Security Assertion Markup Language)](#saml-security-assertion-markup-language)

-----------------

# Types of Authentication Credentials
|Element|Description|Scenario|
|:---|:---|:---|
|Somewhere you are|Restrict access to a specific location|Access to a building|
|Something you have|Restrict access to a specific object|Access to a safe|
|Something you know|Restrict access to a specific piece of information|Password|
|Something you are|Restrict access to a specific biological characteristic|Fingerprint|
|Something you exhibit|Restrict access to a specific behavior|Typing speed|
|Something you can do|Restrict access to a specific action|Signature|


## Something you know: Passwords
- Passwords are the most common form of authentication
- Passowords provide only weak authentication because they are easily compromised and always under attack
- Password Weaknesses
   - Weakness of Passwords is linked to human nature
     - Human only can remember a limited number of passwords

- Long, complex passwords are most secure 
   - But they are more difficult to remember

- User must remember passwords for many different systems
   - User may write down passwords
   - User may use the same password for multiple systems

- Each account passwords for a different system
   - User may forget passwords
   - User may write down passwords
   - User may use the same password for multiple systems

- Many security policies require users to change passwords frequently
   - User may forget passwords
   - User may write down passwords
   - User may use the same password for multiple systems

- Password Weaknesses
   - User often take shortcuts and use a weak password

- When attempting to create stronger passwords, they generally follow predictable patterns
   - Passwords are often based on the name of a pet, child, or spouse
   - Passwords are often based on a birthday or anniversary
   - Passwords are often based on a favorite sports team or hobby

  ### Attacks on Passwords
  - When users create passwords, a one-way hash is created and stored in the password database
  - Attackers work to steal the file of passwords digests
  - Attackers use a variety of methods to crack passwords
    - Brute force attack
    - Dictionary attack
    - Rainbow table attack
    - They can also use a stolen password to impersonate a user


- The different means of creating candidates include:
    - Brute force attack
    - Dictionary attack
    - Rainbow table attack
    - Password collision attack

### Password Spraying
- Password spraying is a type of brute force attack
- Password spraying is a type of brute force attack
- Brute Force Attack
  - In an automated brute force attack, the attacker uses a script to try a large number of possible passwords
  - In an online brute force attack, the attacker tries a large number of possible passwords by hand
  - In a reverse brute force attack, the attacker tries a small number of common passwords against a large number of user accounts

### Rule Attack 

- A rule attack is a type of dictionary attack
- There are three basic steps in a rule attack:
  - Create a dictionary of words
  - Apply rules to the dictionary
  - Try the resulting passwords

### Dictionary Attack
- In a dictionary attack, the attacker uses a dictionary of words to try to guess a password
- Pre-image attack is a dictionary attack that uses a hash to guess a password
- Birthday attacks the search for two different inputs that produce the same hash
- A rainbow table attack is a type of pre-image attack
- A rainbow table is a pre-computed table for reversing cryptographic hash functions
- A rainbow table attack is a type of pre-image attack
- A rainbow table is a pre-computed table for reversing cryptographic hash functions

### Password Collections
- In 2009, an attacker used an SQL injection attack to steal the password file from RockYou, a social media application
- These passwords gave attackers a large corpus of passwords to use in dictionary attacks
- Using stolen password files to create a dictionary is called a password collection attack


## Smartphone and Security Tokens
- MFA (Multi-Factor Authentication) is a security system that requires more than one method of authentication from independent categories of credentials to verify the user’s identity for a login or other transaction
- Single factor authentication is a security system that requires only one method of authentication
- Using two types of authentication credentials is more secure than using only one

- Most common item used for MFA is a smartphone
- Most common items used for MFA are a smartphone and a security token

  ### Specialized Security Tokens

- A smart card holds a user’s private key and a certificate
- A common access card (CAC) is a smart card used by the U.S. Department of Defense
- In addition to integrated chip, it has a bar code and magnetic strip

- There are disadvantages to using a smart card
  - Smart cards are expensive
  - Smart cards are easily lost or stolen
  - Smart cards are easily damaged
  - Smart card cloning is possible

- Stealing infomation from a smart card is called skimming

- Windowed Token creates a a one-time password that changes a limited time 
- There are two types of windowed tokens
  - Time-based tokens
  - Counter-based tokens
  - HMAC-based one-time password (HOTP) is a counter-based token
  
- Smartphone
   - Once user enter their username and password, their smartphone is the second authentication factor using one of the following methods:
     - SMS text message
     - Mobile app
     - Phone call

- Using a smartphone authentication is not as secure as using a security token
- An OTP received through an SMS text message can be "intercepted" by an attacker
- An malware on a smartphone can intercept an OTP received through an SMS text message

- Secutity Keys
- A security key is a hardware device that provides authentication
- A feature of a security key is attestations
   - Attetations is a key pair that is "burned" into the security key during manufacturing and is specific to each device
   - Some security keys systems require that users must inititally enroll 2 security keys in an event that one is lost or stolen

## Biometrics
### Physiological Biomertics
  - Fingerprint
  - Retina
  - Iris
  - Face
  - Hand
  - Voice
  - DNA

- They uses a person physical characteristics authentication
- Serveral unique characters of a person's body can be used for authentication
  
## Specialized Biometric Devices
- A fingerprint reader is a biometric device that uses a person’s fingerprint to authenticate
- A retinal scanner is a biometric device that uses a person’s retina to authenticate
  - It maps the unique patterns of a person’s retina
  - It uses infrared light to map the unique patterns of a person’s retina

- There are two basic types of fingerprint readers
  - Static fingerprint reader - It takes a picture of a fingerprint
  - Dynamic fingerprint reader - It scans a fingerprint as it is swiped across the reader

![img](https://i.imgur.com/shC1WEP.png)

### Biometric Disadvantages
- Biometric authentication is not perfect
- The cost of biometric devices is high
- Readers have some amount error
  - The false acceptance rate (FAR) is the percentage of times that the biometric device incorrectly accepts an access attempt by an unauthorized user
  - The false rejection rate (FRR) is the percentage of times that the biometric device incorrectly rejects an access attempt by an authorized user

- Biometric devices can be fooled
- A concern with biometrics is the efficacy rate
  - Efficacy may be defined as the benefit of a product or service
  - Critics question the sacrifice of privacy for the benefit of security


## Cogiitive Biometrics
- Cognitive biometrics relates to perception, thought, learning, and memory (understanding the mind)
- It is considered easier for the user to remember because it is based on the user's life experiences 
  - For example "What was the name of your first pet?"
  - For example "What was the name of your first school?"

- Congnitive biometrics is also called knowledge-based authentication (KBA)

- Picture Password was introduced by Microsoft for Windows 10 touch-enabled decives
  - It is a combination of a picture and a gesture
  - User can select a pictre tp ise fpr which there should be 10 points of contact that can be served as landmarks or places to touch
    - But in reality, this feature is not very secure and it feels like a gimmick

## Behavioral Biometrics
- Behavioral biometrics is based on a person’s behavior
- A type of behavioual biometrics is keystroke dynamics
  - Attempts to recognize user typing patterns

- Keystroke dynamics is a type of behavioral biometrics
  - Dwelling time is the length of time a key is pressed
  - Flight time is the length of time between key presses

- Keystroke dynamics holds a great amount of potential for authentication as it requires no additional hardware

# Authentication Solutions
- Service providers offer authentication solutions
- Authentication solutions are available from service providers

# Password Security
- Protecting Password Digest
  - One method of protecting password digests is to use a salt, which consists of random bits added to the password before creating the hash
  - Passwords can be protected by adding a rando mstring to the user's cleartext password befre it is hashed
  - Salts make dictionary attacks more difficult and brute force attacks more time consuming and limit the impact of rainbow table attacks

- Another method is to use key stretching 
  - Key stretching is a technique that makes a password hash more secure by adding a random value to the password before hashing it
  - The two most common key stretching algorithms are PBKDF2 and bcrypt

### Managing Passwords
- The most critical factor in a strong password is length
- The longer a password is, the more attempts an attacker must make to guess it
- Due to the limitation of a human memory,security experts universally recommend using a password manager
- Techniques for managing passwords include:
  - Password reuse
  - Password manager
  - Password vault
  - Password synchronization
  - Password reset
  - Password recovery

- A password **vault** is a secure storage location for passwords (Also known as a password manager)
- Three basic types of password  vaults:
  - Password generators 
  - Online password vaults
  - Password management applications

- Password keys are more secure hardware-based password vaults to store a password
- A hardware security module (HSM) is a physical computing device that safeguards and manages digital keys for strong authentication and provides cryptoprocessing
   - A HSM can also perform encription and decryption for digital signatures, authentication, and other cryptographic functions for backup sensitive data, such as digital certificates, encryption keys, and passwords

![img](https://i.imgur.com/16TvaIh.png)

- Passkeys are more secure hardware-based password vaults to store a password 

### Single Sign-On (SSO)
- Single sign-on (SSO) is a session and user authentication service that permits a user to use one set of login credentials (e.g., name and password) to access multiple applications
- Identity and access management (IAM) is a framework of policies and technologies for ensuring that the proper people in an enterprise have the appropriate access to technology resources
- It is called federated (sometimes its called federated identity management or FIM) when networks are owned by different entities
- Single sign-on (SSO) is a session and user authentication service that permits a user to use one set of login credentials (e.g., name and password) to access multiple applications

### Authentication Services
- Different types of authentication services include:
  - Kerberos (Microsoft Active Directory)
  - RADIUS (Remote Authentication Dial-In User Service)
  - TACACS+ (Terminal Access Controller Access Control System Plus)
  - LDAP (Lightweight Directory Access Protocol)
  - SAML (Security Assertion Markup Language) 


### RADUIS


- RADIUS was initially designed for remote dial-in access to a corporate network.
- A RADIUS client, such as a wireless access point (AP), is responsible for sending user credentials and connection parameters to the RADIUS server.
- RADIUS user profiles are stored in a central database that can be shared among all remote servers.
- The use of a central RADIUS service offers several advantages, including increased security due to a single administered network point and easier tracking of usage for billing and network statistics.


![img](https://i.imgur.com/EFtvkHp.png)

### Kerberos

- Kerberos is an authentication system developed at MIT.
- It utilizes encryption and authentication mechanisms to ensure security.
- The analogy of using a driver's license to cash a check is used to explain how Kerberos works.
- Kerberos tickets have characteristics that make them difficult to copy, contain user-specific information, list restrictions, and have an expiration date.
- Kerberos is commonly used when a user wants to access a network service that requires authentication.


### TACACS (Terminal Access Controller Access Control System)
 is a remote authentication protocol that provides centralized access control for network devices. Here's some information about TACACS:

- TACACS was initially developed by Cisco Systems and is now an industry-standard protocol.
- It separates authentication, authorization, and accounting (AAA) functions into separate processes.
- TACACS uses a client-server model, where the client device (such as a network switch or router) sends authentication requests to the TACACS server for verification.
- The TACACS server is responsible for authenticating the user's credentials, authorizing their access to specific resources, and logging accounting information.
- TACACS supports various authentication methods, including password-based authentication and token-based authentication.
- It provides granular control over user access rights and privileges, allowing administrators to define specific policies and restrictions.
- TACACS can be used to manage access to network devices, control administrative privileges, and track user activity for auditing purposes.

### Directory Services
- A directory service is a network service that stores, organizes, and provides access to information in a directory.
- Directory service make it easier to grant privileges to users, devices, and applications.
### SAML (Security Assertion Markup Language)
 is an XML-based open standard data format for exchanging authentication and authorization data between parties, in particular, between an identity provider and a service provider.
 - SAML allows user's login credentials to be shared between multiple web application instead of being stored on each application's database.
 - SAML is used extensively in cloud computing applications for example Business-to-Business (B2B) and Business-to-Customer (B2C) applications.


