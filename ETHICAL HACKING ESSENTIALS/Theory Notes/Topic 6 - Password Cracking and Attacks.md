# Password Hacking 

# Table of Contents


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