# Topic 2a Threat attacks on endpoints

# Table of Contents


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
  
# Backdoor Evade
- A backdoor is a method of bypassing normal authentication procedures.
- Logic bomb is a piece of code intentionally inserted into a software system that will set off a malicious function when specified conditions are met.
- Rootkit is a collection of computer software, typically malicious, designed to enable access to a computer or an area of its software that is not otherwise allowed (for example, to an unauthorized user) and often masks its existence or the existence of other software.
- Bootkit is a type of rootkit that infects the master boot record (MBR).

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
- Unusual system bandwidth spikes
- Unusual system packet loss spikes
- Unusual system jitter spikes
- Unusual system latency drops
- Unusual system response time drops
- Unusual system throughput drops
- Unusual system bandwidth drops
- Unusual system packet loss drops
- Unusual system jitter drops
- Unusual system latency fluctuations
- Unusual system response time fluctuations
- Unusual system throughput fluctuations
- Unusual system bandwidth fluctuations
- Unusual system packet loss fluctuations
- Unusual system jitter fluctuations
- Unusual system latency patterns
- Unusual system response time patterns
- Unusual system throughput patterns
- Unusual system bandwidth patterns
- Unusual system packet loss patterns
- Unusual system jitter patterns
- Unusual system latency trends
- Unusual system response time trends
- Unusual system throughput trends
- Unusual system bandwidth trends
- Unusual system packet loss trends
- Unusual system jitter trends
- Unusual system latency anomalies
- Unusual system response time anomalies
- Unusual system throughput anomalies
- Unusual system bandwidth anomalies
- Unusual system packet loss anomalies
- Unusual system jitter anomalies
- Unusual system latency outliers
- Unusual system response time outliers
- Unusual system throughput outliers
- Unusual system bandwidth outliers
- Unusual system packet loss outliers
- Unusual system jitter outliers
- Unusual system latency clusters
- Unusual system response time clusters
- Unusual system throughput clusters
- Unusual system bandwidth clusters
- Unusual system packet loss clusters
- Unusual system jitter clusters
- Unusual system latency patterns
- Unusual system response time patterns
- Unusual system throughput patterns
- Unusual system bandwidth patterns
- Unusual system packet loss patterns
- Unusual system jitter patterns
- Unusual system latency trends
- Unusual system response time trends
- Unusual system throughput trends
- Unusual system bandwidth trends
- Unusual system packet loss trends
- Unusual system jitter trends
- Unusual system latency anomalies
- Unusual system response time anomalies
- Unusual system throughput anomalies
- Unusual system bandwidth anomalies
- Unusual system packet loss anomalies
- Unusual system jitter anomalies
- Unusual system latency outliers
- Unusual system response time outliers
- Unusual system throughput outliers
- Unusual system bandwidth outliers
- Unusual system packet loss outliers
- Unusual system jitter outliers
- Unusual system latency clusters
- Unusual system response time clusters
- Unusual system throughput clusters
- Unusual system bandwidth clusters
- Unusual system packet loss clusters
- Unusual system jitter clusters

These symptoms may not always indicate a malware infection, but they are worth investigating if you suspect that your system has been compromised.


