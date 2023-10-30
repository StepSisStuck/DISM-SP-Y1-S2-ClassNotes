# Topic 3 - Authentication Credentials


# Table of Contents

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
  
### Specialized Biometric Devices
- A fingerprint reader is a biometric device that uses a person’s fingerprint to authenticate
- A retinal scanner is a biometric device that uses a person’s retina to authenticate
  - It maps the unique patterns of a person’s retina
  - It uses infrared light to map the unique patterns of a person’s retina

- There are two basic types of fingerprint readers
  - Static fingerprint reader - It takes a picture of a fingerprint
  - Dynamic fingerprint reader - It scans a fingerprint as it is swiped across the reader


