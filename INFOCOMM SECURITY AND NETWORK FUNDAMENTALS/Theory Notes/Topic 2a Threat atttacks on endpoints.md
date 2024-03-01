# Topic 2a Threat attacks on endpoints

# Table of Contents
- [Topic 2a Threat attacks on endpoints](#topic-2a-threat-attacks-on-endpoints)
- [Table of Contents](#table-of-contents)
- [Different type of attacks on endpoints](#different-type-of-attacks-on-endpoints)
- [Evolution of malware](#evolution-of-malware)
- [Imprisonment malware](#imprisonment-malware)
  - [Ransomeware](#ransomeware)
  - [Cryptomalware](#cryptomalware)
- [Launch malware](#launch-malware)
  - [Fileless virus](#fileless-virus)
  - [Worm](#worm)
  - [Bot](#bot)
- [Snoop](#snoop)
  - [Spyware](#spyware)
  - [Keylogger](#keylogger)
- [Deceive malware](#deceive-malware)
- [Evade malware](#evade-malware)
  - [Backdoor](#backdoor)
  - [Logic bomb](#logic-bomb)
  - [Rootkit](#rootkit)
- [Symptoms of malware infection](#symptoms-of-malware-infection)
- [Application Attacks](#application-attacks)
- [Script](#script)
- [Injection](#injection)
- [Request Forgery](#request-forgery)
  - [Server-side Request Forgery (SSRF)](#server-side-request-forgery-ssrf)
- [Attacks on Software](#attacks-on-software)
  - [Memory Vulnerabilities](#memory-vulnerabilities)
  - [Improper Exception Handling](#improper-exception-handling)
  - [Attacks on External Software Components](#attacks-on-external-software-components)
- [What are Artificial Intelligence (AI) and Machine Learning (ML)?](#what-are-artificial-intelligence-ai-and-machine-learning-ml)
  - [Uses in Cybersecurity](#uses-in-cybersecurity)
- [Summary](#summary)


----------------------------------------
# Different type of attacks on endpoints
- **Malware** is a software that is intended to damage or disable computers and computer systems without a user's knowledge. Malware includes computer viruses, worms, trojan horses, ransomware, spyware and other malicious programs.
- **Ransomware** is a type of malware that prevents or limits users from accessing their system, either by locking the system's screen or by locking the users' files unless a ransom is paid. More modern ransomware families, collectively categorized as crypto-ransomware, encrypt certain file types on infected systems and forces users to pay the ransom through certain online payment methods to get a decrypt key.
- **Spyware** is a type of malware that is installed on a computer without the knowledge of the owner in order to collect the owner's private information. Spyware is known to change computer settings, resulting in slow connection speeds, different home pages, and/or loss of Internet or functionality of other programs.
- **Adware** is a type of malware that bombards you with endless ads and pop-up windows that could potentially be dangerous for your device. Adware is often bundled with free software or games that are downloaded from the Internet.
- **Botnet** is a number of Internet-connected devices, each of which is running one or more bots. Botnets can be used to perform distributed denial-of-service attack (DDoS attack), steal data, send spam, and allows the attacker to access the device and its connection.
- **Rootkit** is a collection of computer software, typically malicious, designed to enable access to a computer or an area of its software that is not otherwise allowed (for example, to an unauthorized user) and often masks its existence or the existence of other software.
- **Trojan** is a type of malware that is often disguised as legitimate software. Trojans can be employed by cyber-thieves and hackers trying to gain access to users' systems. Users are typically tricked by some form of social engineering into loading and executing Trojans on their systems.
- **Virus** is a type of malware that, when executed, replicates by reproducing itself or infecting other programs by modifying them. Infecting computer programs can include as well, data files, or the "boot" sector of the hard drive. When this replication succeeds, the affected areas are then said to be "infected" with a computer virus.
- **Worm** is a type of malware that replicates itself in order to spread to other computers. Often, it uses a computer network to spread itself, relying on security failures on the target computer to access it. Unlike a computer virus, it does not need to attach itself to an existing program.
- **Keylogger** is a type of surveillance software (considered to be either software or spyware) that has the capability to record every keystroke you make to a log file, usually encrypted. A keylogger recorder can record instant messages, e-mail, and any information you type at any time using your keyboard. The log file created by the keylogger can then be sent to a specified receiver.
- **Backdoor** is a method of bypassing normal authentication procedures. Once a system has been compromised, one or more backdoors may be installed in order to allow access in the future, invisibly to the user.
- **Logic bomb** is a piece of code intentionally inserted into a software system that will set off a malicious function when specified conditions are met. For example, a programmer may hide a piece of code that starts deleting files (such as a salary database trigger), should they ever be terminated from the company.
- **Rooting** is the process of allowing users of smartphones, tablets and other devices running the Android mobile operating system to attain privileged control (known as root access) over various Android subsystems. As Android uses the Linux kernel, rooting an Android device gives similar access to administrative (superuser) permissions as on Linux or any other Unix-like operating system such as FreeBSD or macOS.
- **Jailbreaking** is the privilege escalation of an Apple device for the purpose of removing software restrictions imposed by Apple on iOS, iPadOS, tvOS and watchOS operating systems. This is typically done by using a series of kernel patches. Jailbreaking permits root access in Apple's mobile operating system, allowing the installation of software that is unavailable through the official Apple App Store.

----------------------------------------

# Evolution of malware 
- Malware is constantly evolving and becoming more sophisticated and harder to detect.
- Malware is often used to steal sensitive information, send spam, and commit fraud.
- One of the attempts to classify malware is to group them into families based on their behavior.
    - Imprisonment malware
    - Launch malware
    - Snooping malware
    - Decieve malware
    - Evade malware

----------------------------------------

# Imprisonment malware
- Imprisonment malware is designed to prevent the user from accessing the system or data.
- The malware may lock the system or encrypt the data.
- 2 Types of malware that imprisons:
##  Ransomeware
- Ransomeware prevents users from accessing their system or data until a ransom is paid.
- Some ransomeware pretend to be law enforcement agencies and accuse the user of illegal activities.
- Some ransomeware encrypts the data and demands a ransom to decrypt the data.
- Some ransomeware encrypts the master boot record (MBR) and demands a ransom to decrypt the MBR.

## Cryptomalware
- Cryptomalware is a type of ransomeware that encrypts the data on the system.
- The cost for the key to unlock the data is usually in the form of a cryptocurrency such as Bitcoin.
- Cryptomalware is often delivered through phishing emails or drive-by downloads.
- New variants of cryptomalware are constantly being developed.
- Some cryptomalware will delete the data if the ransom is not paid within a certain time period.

![img](https://i.imgur.com/k6caZ13.png)
![img](https://i.imgur.com/OebnFOq.png)

----------------------------------------

# Launch malware
- Malware that infects a system and then launches an attack on other systems.
- Virus
  - There are two types of viruses:
    - File-based viruses
    - Fileless viruses

- A file-based virus is a virus that infects executable files.
- A fileless virus is a virus that does not infect executable files.
- A fileless virus is also known as a memory-resident virus.
- A fileless virus is loaded into memory and then infects other files in memory.
## Fileless virus
- A fileless virus does not attach itself to a file instead takes advantage of a vulnerability in an application.
    - It does not infect the file system, instead it infects the memory by injecting malicious code into a running process.

- Advantages of a fileless virus:
    - It is more difficult to detect.
    - It is more difficult to remove.
    - It is more difficult to analyze.
    - It is more difficult to reverse engineer.
    - It is more difficult to sandbox.
    - It is more difficult to emulate.
    - It is more difficult to debug.
    - It is more difficult to scan.

- A fileless virus is often delivered through phishing emails or drive-by downloads.
## Worm
- A worm is a type of malware that replicates itself in order to spread to other computers.
- Designed to spread quickly through a network.
- A worm does not need to attach itself to an existing program.
- A worm can spread without user interaction.
- Today's worms can leave backdoors on infected systems.
- Active worms can consume a large amount of network bandwidth.

## Bot
- A bot is a type of malware that is used to perform automated tasks on a network.
- A bot is also known as a zombie.
- A bot is often used to perform distributed denial-of-service (DDoS) attacks.
- A bot can be used to send spam.
- A bot can be used to steal data.

# Snoop 
- Two common types of snooping malware are:
    - Keylogger
    - Spyware

## Spyware
- Spyware is a type of malware that is installed on a computer without the knowledge of the owner in order to collect the owner's private information.
- Spyware is known to change computer settings, resulting in slow connection speeds, different home pages, and/or loss of Internet or functionality of other programs.
- Spyware is often installed by a Trojan horse.

## Keylogger
- A keylogger is a type of surveillance software (considered to be either software or spyware) that has the capability to record every keystroke you make to a log file, usually encrypted.
- A keylogger recorder can record instant messages, e-mail, and any information you type at any time using your keyboard.
- The log file created by the keylogger can then be sent to a specified receiver.
- A keylogger can be either software or hardware.

![img](https://i.imgur.com/Wa0Ylu7.png)

----------------------------------------

  
# Deceive malware
- Deceive malware is designed to deceive the user.
- Example includes Trojan horse, Remote Access Trojan (RAT), and backdoor.
    - A Trojan horse is a type of malware that is disguised as legitimate software.
    - A Trojan horse is often delivered through phishing emails or drive-by downloads.
    - A Trojan horse does not replicate itself.
  

- Remote Access Trojan (RAT) is a type of Trojan horse that allows an attacker to take control of the infected system.
- A RAT can be used to steal data, send spam, and commit fraud.
- A RAT can be used to perform distributed denial-of-service (DDoS) attacks.
- A RAT can be used to install other malware.


# Evade malware

- Evade malware is designed to evade detection by antivirus software.
- Example includes rootkit, logic bomb, and bootkit.
  
## Backdoor 
- A backdoor is a method of bypassing normal authentication procedures.
- Logic bomb is a piece of code intentionally inserted into a software system that will set off a malicious function when specified conditions are met.
- Rootkit is a collection of computer software, typically malicious, designed to enable access to a computer or an area of its software that is not otherwise allowed (for example, to an unauthorized user) and often masks its existence or the existence of other software.
- Bootkit is a type of rootkit that infects the master boot record (MBR).

## Logic bomb
- A logic bomb is a piece of code intentionally inserted into a software system that will set off a malicious function when specified conditions are met.
- For example, a programmer may hide a piece of code that starts deleting files (such as a salary database trigger), should they ever be terminated from the company.

## Rootkit
- A rootkit is a malware that can hide its presence and activities in an infected system.
- It dows this by accessing the kernel of the operating system.

----------------------------------------
# Symptoms of malware infection


- Slow computer performance
- Frequent crashes or freezes
- Unusual error messages
- Pop-up ads or unwanted toolbars
- Changes to browser settings or homepage
- Unusual network activity
- Unusual hard drive activity
- Unusual CPU activity
- Unusual RAM usage
- Unusual disk usage
- Unusual network traffic
- Unusual system behavior
- Unusual system messages
- Unusual system crashes
- Unusual system restarts
- Unusual system shutdowns
- Unusual system errors
- Unusual system warnings
- Unusual system logs
- Unusual system files
- Unusual system processes
- Unusual system services
- Unusual system registry entries
- Unusual system drivers
- Unusual system applications
- Unusual system utilities
- Unusual system tools
- Unusual system settings
- Unusual system configurations
- Unusual system updates
- Unusual system patches
- Unusual system upgrades
- Unusual system backups
- Unusual system restores
- Unusual system scans
- Unusual system checks
- Unusual system audits
- Unusual system logs
- Unusual system reports
- Unusual system notifications
- Unusual system alerts
- Unusual system alarms
- Unusual system events
- Unusual system tasks
- Unusual system schedules
- Unusual system processes
- Unusual system threads
- Unusual system handles
- Unusual system resources
- Unusual system memory usage
- Unusual system disk usage
- Unusual system network usage
- Unusual system CPU usage
- Unusual system GPU usage
- Unusual system I/O usage
- Unusual system latency
- Unusual system response time
- Unusual system throughput
- Unusual system bandwidth
- Unusual system packet loss
- Unusual system jitter
- Unusual system latency spikes
- Unusual system response time spikes
- Unusual system throughput spikes

These symptoms may not always indicate a malware infection, but they are worth investigating if you suspect that your system has been compromised.

----------------------------------------





# Application Attacks

- Another category of attacks look for vulnerabilities in applications.
    - Common Targets of attackers using application attacks are Internet web servers and web browsers.

- Web servers are often targeted because they are accessible from the Internet and they are often not patched or updated regularly.

# Script
- In a cross-site scripting (XSS) attack, the attacker injects malicious code into a web application.
- An attacker can use XSS to send a malicious script to an unsuspecting user.

- The end user's browser has no way to know that the script should not be trusted, and will execute the script.

# Injection
- An injection attack is a type of attack that involves injecting code into a vulnerable web application.

- One of the most common types of injection attacks is a Structured Query Language (SQL) injection attack.
- An attacker can use a SQL injection attack to bypass authentication or to retrieve data from a database.

- SQL injection target SQL databases by introducing malicious code into database queries.
- By entering crafted SQL statement as user input, an attacker can execute malicious SQL statements, and they can be extracted or the existing data can be modified.

# Request Forgery
- Request Forgery is a type of attack that involves creating and submitting unauthorized requests to a vulnerable web application.
- There are 2 type of Request Forgery:
    - Cross-site request forgery (CSRF)
    - Server-side request forgery (SSRF)

- Cross-site Request Forgery (CSRF) is a type of attack that involves creating and submitting unauthorized requests to a vulnerable web application.
   - CSRF takes advantage of the trust that a web application has for a user's browser.
   - If a user is logged into a web application, the web application will trust any request that is sent from the user's browser.

![img](https://i.imgur.com/7F9OwTS.png)


  ## Server-side Request Forgery (SSRF)
  - An SSRF takes advantage of the trust that a web application has for a server.
  - SSRF attacks exploit the trust that a web application has for a server.
  - If a web application trusts a server, it will trust any request that is sent to that server.
  - An attacker can use an SSRF attack to send requests to internal servers that are not accessible from the Internet.

|Attack Name| Attack Target| Purpose of Attack|
|---|---|---|
|CSRF(Cross-site Request Forgery)|User's browser|To send unauthorized requests to a vulnerable web application|
|SSRF(Server-side Request Forgery)|Server|To send unauthorized requests to internal servers that are not accessible from the Internet|

# Attacks on Software
- Other attacks are directly targeted at software that focusd on exploiting vulnerabilities in software.
- These include:
   - Exploit Memory Vulnerabilities
   - Improper Exception Handling
   - External Software Component

## Memory Vulnerabilities
- Memory vulnerabilities are vulnerabilities that allow an attacker to access memory that they should not be able to access.
- Some memory-related attacks are called resource exhaustion attacks because they exhaust the resources of a system thus interfering with the normal operation of the system in programs like RAM, CPU, and disk space.

- Other memory-related attacks are called buffer overflow attacks because they overflow the buffer of a system.
- A buffer overflow attack occurs when a program tries to store more data in a buffer than it was intended to hold.

- In an interger overflow attack, an attacker can use an integer overflow to wrap a variable to a smaller value.
## Improper Exception Handling
- Some attacks are the result of poor coding on the part of the developer.
- Improper exception handling occurs when a developer does not properly handle exceptions.
- An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions.

- An exception can be caused by a variety of factors, including:
    - Invalid input
    - Invalid output
    - Invalid code
    - Invalid operation
    - Invalid data
    - Invalid instruction
    - Invalid memory access
    - Invalid memory address
    - Invalid memory allocation
    - Invalid memory deallocation
    - Invalid memory reference
    - Invalid memory write
    - Invalid memory read
    - Invalid memory write
    - Invalid memory read
    - Invalid memory write
    - Invalid

## Attacks on External Software Components
- Some attacks are the result of vulnerabilities in external software components.
- These include:
    - Driver Vulnerabilities
    - Virtualization Vulnerabilities
    - Cloud Vulnerabilities
    - Mobile Vulnerabilities
    - IoT Vulnerabilities
    - API Vulnerabilities
    - Dynamic Link Library (DLL) Vulnerabilities
# What are Artificial Intelligence (AI) and Machine Learning (ML)?
- Artificial Intelligence (AI) is the ability of a computer system to perform tasks that normally require human intelligence.
- A recongnized of AI is Machine Learning (ML).
    - Machine Learning (ML) is the ability of a computer system to learn and improve from experience without being explicitly programmed.
- ML also involves the use of algorithms that can learn from and make predictions on data.
   - If something attempted does not work, then it determines what went wrong and tries again.

## Uses in Cybersecurity
- AI and ML are used in cybersecurity to detect and prevent cyber attacks.
- AI and ML are used to detect and prevent cyber attacks.
- Email security products use AI and ML to detect and prevent phishing attacks.
- AI and ML is an advantage to conbat cyber attacks because it can detect and prevent attacks that have never been seen before.


# Summary
 Topic 2a Threat Attacks on Endpoints discusses the importance of securing an operating system through proper security configuration and confinement tools. The document highlights the typical security configuration of an OS, which includes disabling unnecessary ports and services, disabling default accounts/passwords, and employing least functionality. 

The document also mentions the Tamper Protection security feature in Windows 10, which prevents Windows security settings from being changed or disabled by a threat actor who modifies the registry. Additionally, a Group Policy setting can prevent access to registry editing tools.

Finally, the document discusses confinement tools, which are used to restrict malware. These tools include application whitelisting/blacklisting, sandbox, and quarantine.
