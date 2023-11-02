# Topic 3 OS Enumeration

# Table of Contents
- [Topic 3 OS Enumeration](#topic-3-os-enumeration)
- [Table of Contents](#table-of-contents)
- [Valunerability Research](#valunerability-research)
- [Common Vulnerability and Exposure (CVE)](#common-vulnerability-and-exposure-cve)
- [Vulenrability Archives](#vulenrability-archives)
- [Test the Vulnerability](#test-the-vulnerability)
- [NetBIOS Basic](#netbios-basic)
  - [Network Basic Input/Output System (NetBIOS)](#network-basic-inputoutput-system-netbios)
  - [NetBIOS Names](#netbios-names)
- [Enumeration](#enumeration)
- [Port Scanning is part of enumeration](#port-scanning-is-part-of-enumeration)
- [NetBIOS Enumeration Tools](#netbios-enumeration-tools)
  - [Additional Enumeration Tools](#additional-enumeration-tools)
- [Hyena](#hyena)
- [Nessus](#nessus)
- [Open Vulnerability Assessment System (OpenVAS)](#open-vulnerability-assessment-system-openvas)
  - [OpenVAS Architecture](#openvas-architecture)
- [Remote Procedure Call (RPC) Enumeration](#remote-procedure-call-rpc-enumeration)
- [Server Message Block (SMB) Enumeration](#server-message-block-smb-enumeration)
    - [Hacking tools to use](#hacking-tools-to-use)
- [Common Internet File System (CIFS) Enumeration](#common-internet-file-system-cifs-enumeration)
    - [Server Security Method](#server-security-method)
- [Understanding SAMBA](#understanding-samba)
    - [Best way to protect against SAMBA](#best-way-to-protect-against-samba)
- [Sticky Keys and Utility Manager](#sticky-keys-and-utility-manager)
- [Windows Authentication - LM HASH](#windows-authentication---lm-hash)
  - [Windows Authentication - NTLM HASH](#windows-authentication---ntlm-hash)
    - [NTVLMv2](#ntvlmv2)
    - [Kerberos](#kerberos)
- [Windows Password Dumping](#windows-password-dumping)
- [Vulnerability in Microsoft Services](#vulnerability-in-microsoft-services)
- [Patching Systems](#patching-systems)
- [Antivirus Software](#antivirus-software)
  - [List of Antivirus Software](#list-of-antivirus-software)
- [Enable Logging and Review Logs](#enable-logging-and-review-logs)
- [Disable Unused Services](#disable-unused-services)
  - [Here are some simplified security best practices:](#here-are-some-simplified-security-best-practices)
- [Backdoors](#backdoors)
  - [Netcat](#netcat)
  - [Here is the list of \*nix operating systems and their variations:](#here-is-the-list-of-nix-operating-systems-and-their-variations)
- [Linux OS Vulnerabilities](#linux-os-vulnerabilities)
  - [Remote Access Attacks on Linux Systems](#remote-access-attacks-on-linux-systems)
  - [Linux Trojans Programs](#linux-trojans-programs)


--------------------------------------------------
# Valunerability Research

- Important to know what OS and version is running on the target machine
- To view vulnerabilities of OS and services running on the target machine
- Sources to get
    - Online databases
    - IRC
    - Fourms 
    - News groups
    - Underground sites

# Common Vulnerability and Exposure (CVE)

- CVE is a list of publicly known information security vulnerabilities and exposures
- CVE identifiers are unique, common names for publicly known information security vulnerabilities and exposures
- CVE identifiers have a status of either Candidate, Entry, or Retired
- CAN - indicate that is under review

# Vulenrability Archives
http://cve.mitre.org/cve/
http://www.osvdb.org/
http://www.packetstormsecurity.com/
http://archives.neohapsis.com/
http://www.securityfocus.com/search
http://neworder.box.sk/
http://www.milw0rm.com
http://research.eeye.com
http://www.securityforest.com


# Test the Vulnerability
- Many tools are available to test the vulnerability
- Using serveral tools will give you a better idea of the vulnerability
  

# NetBIOS Basic

## Network Basic Input/Output System (NetBIOS)
- Allows Programming Interface (API) to allow applications on separate computers to communicate over a LAN
- Allows applications to run on different computers and operating systems
- Used to share files, printers, and logon to domain controllers

## NetBIOS Names
- Computer names on Windows system
- Limited to 16 characters
- Last character is a special character
- Must be unique on the network

# Enumeration 
- Process of gathering information about a target network
- Used to create a network map
- Discover resources on the network
# Port Scanning is part of enumeration
- Intrusive process 
- Involves connecting to the target machine

# NetBIOS Enumeration Tools
- Nbtstat
   - Powerful tool for enumerating NetBIOS information
   - Display NetBIOS table

- Netview command 
   - Shows wheather there are any shared resources on the target machine

- Use information gathered to find vulnerabilities
  - Use IP address obtain when port scanning to perform a NetBIOS enumeration

```bash
nbtstat -a salesrep
```

- The following information is displayed:
  ```
    Local Area Connection:
    Node IpAddress: [192.168.0.100] Scope Id: []
    NetBIOS Remote Machine Name Table
    | Name | Type | Status |
    |------|------|--------|
    |SALESREP <00> | UNIQUE | Registered |
    |SALESREP <03> | UNIQUE | Registered |
    |SALESREP <20> | UNIQUE | Registered |
    |SALESREP <1E> | GROUP | Registered |
    |SALESREP <1D> | UNIQUE | Registered |
    |ZIONBANK <00> | GROUP | Registered |
    |ZIONBANK <1D> | UNIQUE | Registered |
    |ADMINISTRATOR <03> | UNIQUE | Registered |
    |IS~ADMINISTRATOR <00> | UNIQUE | Registered |
    |..__MSBROWSE__. <01> | GROUP | Registered |
    |INet~Services <1C> | GROUP | Registered |

    MAC Address = 00-00-00-00-00-00
    C:\Users\user>_
    ```

```bash
net view
```

- The following information is displayed:
  ```
    Server Name     Remark
    ----------------------------------------
    \\SALESREP      Manager
    \\ZIONBANK      Zion Bank
    \\ADMINISTRATOR
    \\SERVER1       Server1
    The command completed successfully.
    C:\Users\user>net view ?
    The syntax of this command is:
    NET VIEW
    [\\computername [/CACHE] | [/ALL] | /DOMAIN[:domainname]]
    NET VIEW /NETWORK:NW [\\computername]

    C:\Users\user>_
    ```
- To view the shared resources on a specific machine
    ```bash
    net view \\192.168.0.106
    ```
- The following information is displayed:
  ```
    Shared resources at \\192.168.0.106
    Share name     Type     Used as  Comment
    ------------------------------------------
    ADMIN$         Disk     Remote Admin
    C$             Disk     Default share
    IPC$           IPC      Remote IPC
    The command completed successfully.
    C:\Users\user>_
    ```

```bash
net use?
```

- Used to connect to a shared resource

```
The syntax of this command is:

NET USE
[devicename | *] [\\computername\sharename[\volume] [password | *]]
        [/USER:[domainname\]username]
        [/USER:[dotted domain name\]username]
        [/USER:[username@dotted domain name]
        [/SMARTCARD]
        [/SAVECRED]
        [[/DELETE] | [/PERSISTENT:{YES | NO}]]
NET USE {devicename | *} [password | *] /HOME

NET USE [/PERSISTENT:{YES | NO}]

C:\Users\user>_
```

## Additional Enumeration Tools
- Nessus 
- DumpSec
- NetScanTools Pro
- OpenVAS

# Hyena 
www.systemtools.com/hyena

- Hyena is a tool that can be used to enumerate Windows systems
- Shows shares and user logon information for Windows Server and domain controllers
- Displays graphical representation of the network
   - Microsoft Terminal Services
   - Microsoft Exchange
   - Microsoft Windows Network
   - Web Services
   - Find User/Group


![img](https://i.imgur.com/bwbM4zk.png)

# Nessus 
www.tenable.com/products/nessus
- Allows enumeration of different OSs on a large network
- Nessus Identifies
   - NetBIOS name in use
   - Shared resources
   - User accounts
   - Vulnerabilities 
   - Also offers solutions to those vulnerabilities
   - OS version 
   - OS vulnerabilities
   - Firewall vulnerabilities





# Open Vulnerability Assessment System (OpenVAS)
www.openvas.org

- OpenVAS is a framework of several services and tools offering a comprehensive and powerful vulnerability scanning and vulnerability management solution
- What can OpenVAS do 
    - Vulnerability scanning with a large database of known vulnerabilities
    - Management of large-scale vulnerability scans
    - Reporting of scan results
    - Integration with other tools
    - OpenVAS is a fork of Nessus

- Network Vulnerability Test (NVTs)
    - Scans for vulnerabilities
    - Can be downloaded

## OpenVAS Architecture
Sometimes the network vulnerability test send an exploit to the target machine that causes the machine to crash

OpenVAS allows you to configure the network vulnerability test to not send the exploit to the target machine

You may choose only "safe" test if you do not want to risk crashing the target machine (e.g. if it is a web server running a production website)

All scanning activities are logged and they will generate a lot of traffic on the network

When you run a scan against a production networks, be prepared to have your firewalls, intrusion detection systems, log management systems, and other security devices to be triggered

Your security system should detect the scanning activities and alert you

# Remote Procedure Call (RPC) Enumeration
- RPC is a protocol that allows a program on one computer to run a program on another computer
- RPC is used to share files, printers, and other resources
- RPC uses port 135 
- Examples of worms that exploit RPC
    - Blaster
    - Sasser
    - Welchia
    - Conficker

# Server Message Block (SMB) Enumeration
- SMB is a protocol that allows a program on one computer to run a program on another computer
- Used by wiindows to share files, printers, and other resources
- Usually runs on top of NetBIOS, NetBEUI, or TCP/IP


### Hacking tools to use 
- Nbtstat
- L0phtCrack SMP Packet Capture utility
- SMBRelay

SMB3 introduced in Windows 8 and Windows Server 2012
 


# Common Internet File System (CIFS) Enumeration
CIFS is a protocol that allows a program on one computer to run a program on another computer

- CIFS is a dialect of SMB
   - Remote Procedure Call (RPC) is used to communicate between the client and server
   - Enables computers to share files and printers

Relies on other protocols to handle service announcement, name resolution, authentication, and authorization

### Server Security Method
- Share-level security
   - User must have a valid username and password to access the shared resource 

- User-level security
  - User must have a valid username and password to access the shared resource in local security database

# Understanding SAMBA
- Open-source implementation of the SMB/CIFS networking protocol
- Samba allows sharing resources between Linux and Windows systems
- Samba accessing Microsoft Windows NT, 2000, XP, Vista, and 7
- Samba can be used to share files, printer 13s, and other resources between Linux and Windows systems
- Samba is to "trick" Windows systems into thinking that they are communicating with other Windows systems *NIX resources

### Best way to protect against SAMBA
- Router should filter out all traffic on port
   - Port 137 to 139
   - Port 445


# Sticky Keys and Utility Manager
- Sticky Keys and Utility Manager are accessibility features in Windows
- Pressing the Shift key five times will activate Sticky Keys
- Pressing the Windows key and U will activate Utility Manager
- Hackers can use these features to gain access to a Windows system without using a password

https://www.infosecisland.com/blogview/15031-How-to-Log-In-to-Windows-Without-the-Password.html

# Windows Authentication - LM HASH 

On Windows systems, hashed passwords of local user are stored in SAM (Security Account Manager), in C:\Windows\System32\config\SAM

The LM Hash was previously used to store passwords in Windows

As LM hash is not case sensitive, it is easy to crack, NTLMv2 is used to replace LM hash with a more secure hash

For Windows systems in an Active Directory domain, the hashed passwords of domain users are stored in Active Directory

## Windows Authentication - NTLM HASH
- NTLM hash is used to store passwords in Windows
- They are intoduceed to address the weakness in LM hash
- 128 bit hash
- However, Windows still send LMHash and NTLM hash over the network for backwords compatibility

### NTVLMv2
- NTLMv2 is used to replace LM hash with a more secure hash
- NTLMv2 is used to authenticate users in Windows 2000 and later
- NTLMv2 is more secure than NTLM
- They are cryptographic security protocol

### Kerberos
- Kerberos is a network authentication protocol
- Kerberos is used to authenticate users in Windows 2000 and later
- Kerberos is more secure than NTLMv2
- Kerberos is a cryptographic security protocol
- Kerberos is used in Active Directory domains

# Windows Password Dumping
Software tools exist to dump the Windows Password hashes from the SAM file
- Semdump2 (part of Ophcrack project)
- pwdump
- Meterpreter in Metasploit

# Vulnerability in Microsoft Services
- Internet Information Services (IIS) vulnerabilities
- SQL Server 
   - The SA account with a blank password is created by default and cannot be deleted
   - SQL Server Agent
      - Autorized but unprivileged user can create scheduled jobs to be run by the agent
      - Buffer overflow vulnerability
   - Extended store procedure vulnerability
      - Buffer overflow vulnerability in xp_sprintf
   - Default SQL port 1433
    - Spida worm exploits SQL Server vulnerabilities


# Patching Systems 
- Patching is the process of updating software to fix vulnerabilities
- This is the most important step in securing a system
- Attackers take advantage of unpatched systems to gain access to the system
- Options for small networks
   - Accessing Windows Update Manually
   - Automatic Updates

- Options for large networks
   - Windows Server Update Services (WSUS)
   - System Center Configuration Manager (SCCM)
   - System Center Essentials (SCE)
   - Microsoft Baseline Security Analyzer (MBSA)
   - Intune (cloud-based service)
   - Systems Management Server (SMS)
   - Software Update Services (SUS)

# Antivirus Software
An antivirus software is a program that detects and removes malware from a computer
For small networks 
- Desktop small network
   - Desktop antivirus tools with automatic updates

- For large networks 
    - Enterprise antivirus tools with centralized management and reporting

An antivirus tool is almost useless if it is not updated regularly

## List of Antivirus Software
- Avast
- AVG
- Avira
- Windows Defender
- Bitdefender
- PGP Desktop
- Kaspersky
- McAfee
- Norton
- Sophos
and many more

--------------------------------------------------

# Enable Logging and Review Logs

- Logging is the process of recording events on a computer system
- Important to enable logging on all systems
  - They log Performance
  - Traffic patterns
  - Possible security breaches

Logging can have a negative impact on system performance as it consumes system resources

Reviewing logs regularly is important to detect security breaches or search for signs of a security breach
- Use a log management system to manage logs


# Disable Unused Services
- Disable 
  - Unnecessary services
  - Unnecessary protocols
  - Unnecessary Applications or Scripts
  - Unused applications or services

Requires careful planning and testing
- Close ports but do not disable services

## Here are some simplified security best practices:

- Delete any scripts or sample applications that are not being used.
- Remove any default hidden shares.
- Be cautious of default permissions and adjust them as needed.
- Use a firewall to filter incoming and outgoing network traffic.
- Utilize available security assessment tools to evaluate system security.
- Disable the Guest account and rename the default Administrator account.
- Ensure that all user accounts have strong passwords.
- Set a BIOS password to prevent unauthorized access to the system.
- Encrypt important files to protect sensitive data.
- Secure physical access to the system to prevent unauthorized access.


# Backdoors 
- Backdoors are programs that allow attackers to gain access to a system
- Backdoors are usually installed by attackers
## Netcat
- Netcat is a popular backdoor program
  - Netcat is a networking utility that reads and writes data across network connections
  - Netcat can be used to create a backdoor

You can use it as a 
- Client 
- Server



## Here is the list of *nix operating systems and their variations:

- Solaris
- SunOS
- HP-UX
- Linux
- Ultrix
- AIX
- BSD UNIX
- FreeBSD
- OpenBSD




# Linux OS Vulnerabilities
UNIX-based operating systems like Linux have been around for a long time, which means attackers have had a lot of time to find vulnerabilities in them. There are tools that attackers can use to find these vulnerabilities, and some of these tools can be used specifically against Linux systems. For example, Knoppix is a bootable version of Linux that can be used for this purpose, and Nessus is another tool that can be used to find vulnerabilities in Linux systems.

- Nessus can be used to 
  - Discover vulnerabilities in Linux systems
  - Enumerate Linux systems
  - Discover the root password

They can test Linux computers for vulnerabilities and then exploit those vulnerabilities to gain access to the system. Once they have access to the system, they can install a backdoor program to maintain access to the system.
- Review the CVE and CAN databases to find vulnerabilities in Linux systems


## Remote Access Attacks on Linux Systems 
However, in general, remote access attacks on Linux systems can be carried out by exploiting vulnerabilities in the system's network services or by using brute-force attacks to guess login credentials. Attackers may also use social engineering tactics to trick users into revealing their login credentials or installing malware on their systems. It is important to implement strong security measures, such as using firewalls, keeping software up-to-date, and using strong passwords, to prevent these types of attacks.

## Linux Trojans Programs
- Linux Trojan Programs are sometimes disguised as legitimate programs
- Trojans programs are usually installed by attackers
  - Firewalls and IDSs cannot identify this traffic as malicious
  - Example: Sheepshank 

- It is easier to protect systems from already identified Trojans
  - Use antivirus software
  - Use a firewall
  - Use an IDS

- Rootkits 
   - Contains programs that allow attackers to maintain access to a system
   - They contain Trojen binaries programs ready to be installed on a system with root access to the system
   - Attackers can use rootkits to hide their presence on a system
   - Replace legitimate system files with rootkit files
   - Example LRK5 

- Secure the system to prevent rootkits from being installed
  - Use antivirus software
  - Use a firewall
  - Use an IDS
  - Use a HIDS
  - Use a file integrity checker

http://la-samhna.de/library/rootkits/list.html










