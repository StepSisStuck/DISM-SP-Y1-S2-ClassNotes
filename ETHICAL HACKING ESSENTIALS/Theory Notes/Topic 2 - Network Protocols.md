# Topic 2 - Network Protocols

# Table of Contents
- [Topic 2 - Network Protocols](#topic-2---network-protocols)
- [Table of Contents](#table-of-contents)
- [List to learn in this topic](#list-to-learn-in-this-topic)
- [Kali Linux](#kali-linux)
- [Wireshark](#wireshark)
  - [With Wireshark, you can:](#with-wireshark-you-can)
- [Hypertext Transfer Protocol (HTTP and HTTPS)](#hypertext-transfer-protocol-http-and-https)
  - [HTTP GET with Wireshark](#http-get-with-wireshark)
- [HTTP Methods](#http-methods)
- [NETSTAT](#netstat)
- [Comparing Different Protocols for Remote Login](#comparing-different-protocols-for-remote-login)
- [File Transfer Protocol (FTP)](#file-transfer-protocol-ftp)
- [WinSCP](#winscp)
- [Telnet](#telnet)
- [Secure Shell (SSH), Secure Copy (SCP) and Secure File Transfer Protocol (SFTP), PuTTY](#secure-shell-ssh-secure-copy-scp-and-secure-file-transfer-protocol-sftp-putty)
  - [PuTTY](#putty)
- [Remote Desktop Protocol (RDP) for Remote Login](#remote-desktop-protocol-rdp-for-remote-login)
  - [Remote Desktop Services Example](#remote-desktop-services-example)
  - [Micosoft Remote Desktop](#micosoft-remote-desktop)
- [Summary](#summary)

--------------------
# List to learn in this topic
- Kali Linux
- Wireshark
- Hypertext Transfer Protocol (HTTP and HTTPS)
- Port
- File Transfer Protocol (FTP) and WinSCP
- Telnet
- Secure Shell (SSH), Secure Copy (SCP) and Secure File Transfer Protocol (SFTP), PuTTY
- Remote Desktop Protocol (RDP) for Remote Login


--------------------
# Kali Linux
- A linux distribution designed for penetration testing and digital forensics.
- It is maintained and funded by Offensive Security Ltd.
- They contain a lot of tools for penetration testing and digital forensics.
    - Example: Wireshark, Nmap, Metasploit, etc.

- Also known as Debian-based Linux distribution aim at advanced penetration testing and security auditing.
- Can be run on a virtual machine or installed on a computer or a Live CD/USB.
- Website: https://www.kali.org/
- Download: https://www.kali.org/downloads/
- Rebuilt of BackTrack Linux (2013)

--------------------
# Wireshark
- A free and open-source packet analyzer.
- Network traffic  that can be captured and analyzed offline or live.
- Display information about the packets in the network in Human-readable format.
- Can be used to troubleshoot network problems, examine security problems, debug protocol implementations, etc.

![img](https://i.imgur.com/H17bKYV.png)

## With Wireshark, you can:
- Capture network traffic
- View network traffic
- Filter network traffic
- Analyze network traffic
- Save network traffic
- Export network traffic
- Import network traffic

# Hypertext Transfer Protocol (HTTP and HTTPS)
- HTTP is an application layer protocol for transmitting hypermedia documents, such as HTML.
- HTTP is the foundation of data communication for the World Wide Web.
- HTTP is a client-server protocol where a web browser, the client, requests a web page from a web server, the server, and the server returns the page to the client.

![img](https://i.imgur.com/PE9W2m7.png)

## HTTP GET with Wireshark
- HTTP GET is a request method supported by HTTP used by the World Wide Web.
- The GET method means retrieve whatever information (in the form of an entity) is identified by the Request-URI.
- If the Request-URI refers to a data-producing process, it is the produced data which shall be returned as the entity in the response and not the source text of the process, unless that text happens to be the output of the process.
  
  ![img](https://i.imgur.com/UlX0jw1.png)

 - When a client submit a webform, the data is sent to the server using HTTP GET method.


# HTTP Methods
- GET
   - To request data from a specified resource
   - Most commonly used method in HTTP

- POST
    - To submit data to be processed to a specified resource
    - Commonly used when uploading a file or submitting a completed webform

- HEAD 
    - To ask for a response identical to that of a GET request, but without the response body
    - This is useful for retrieving meta-information written in response headers, without having to transport the entire content

- PUT    
    - To replace all current representations of the target resource with the uploaded content
    - The PUT method is used to upload a file to a server

- DELETE
    - To delete the specified resource
    - The DELETE method deletes the specified resource

- CONNECT
    - To establish a tunnel to the server identified by the target resource
    - The CONNECT method converts the request connection to a transparent TCP/IP tunnel
    - This is usually to facilitate SSL-encrypted communication (HTTPS) through an unencrypted HTTP proxy

- TRACE
    - To perform a message loop-back test along the path to the target resource
    - The TRACE method echoes the received request so that a client can see what (if any) changes or additions have been made by intermediate servers

- OPTIONS
    - To describe the communication options for the target resource
    - The OPTIONS method returns the HTTP methods that the server supports for the specified URL
    - This can be used to check the functionality of a web server by requesting '*' instead of a specific resource

- HTTP and HTTPS
    - HTTP is not secure
    - HTTPS is secure
    - HTTPS is HTTP with encryption
    - HTTPS is HTTP with SSL/TLS
    - HTTPS uses port 443
    - HTTP uses port 80

# NETSTAT
- A command-line network utility tool that displays network connections for Transmission Control Protocol (both incoming and outgoing), routing tables, and a number of network interface (network interface controller or software-defined network interface) and network protocol statistics.
- It is available on Unix-like operating systems including OS X, Linux, Solaris, and BSD, and on Windows NT-based operating systems including Windows XP, Windows Vista, Windows 7, Windows 8, Windows 10 and Windows Server 2003, Windows Server 2008, Windows Server 2010, Windows Server 2013, Windows Server 2016, and Windows Server 2019.

# Comparing Different Protocols for Remote Login
- FTP
- Telnet
- SSH
- RDP
- SCP
- SFTP
- Remote Desktop Protocol (RDP)

# File Transfer Protocol (FTP) 
- A standard network protocol used for the transfer of computer files between a client and server on a computer network.
- The FTP Server normally listens on port 21.
- FTP uses two ports:
    - Port 21 for sending commands
    - Port 20 for sending data

No encryption is used in FTP (Including passwords and data)

Can use alternative port (Port 22) to secure FTP

# WinSCP
- A free and open-source SFTP, FTP, WebDAV, Amazon S3 and SCP client for Microsoft Windows.
- Its main function is secure file transfer between a local and a remote computer.
- Beyond this, WinSCP offers basic file manager and file synchronization functionality.
- For secure transfers, it uses Secure Shell (SSH) and supports the SCP protocol in addition to SFTP.
- Can be used as a graphical user interface (GUI) for the PuTTY suite of utilities.
- Website: https://winscp.net/eng/index.php
- Download: https://winscp.net/eng/download.php

# Telnet
- A protocol used on the Internet or local area network to provide a bidirectional interactive text-oriented communication facility using a virtual terminal connection.
- User data is interspersed in-band with Telnet control information in an 8-bit byte oriented data connection over the Transmission Control Protocol (TCP).
- Telnet was developed in 1969 beginning with RFC 15, extended in RFC 854, and standardized as Internet Engineering Task Force (IETF) Internet Standard STD 8, one of the first Internet standards.
- The name stands for "teletype network".
- Telnet allows a user to login remotely to a server and run programs on that server.
- Telnet is normally run on port 23.
- Another Protocol that is old and insecure (Data is sent in plain text)
- Can use alternative port (Port 22) to secure Telnet

# Secure Shell (SSH), Secure Copy (SCP) and Secure File Transfer Protocol (SFTP), PuTTY
- SSH is a cryptographic network protocol for operating network services securely over an unsecured network.
- Typical applications include remote command-line, login, and remote command execution, but any network service can be secured with SSH.
- SSH provides a secure channel over an unsecured network by using a client–server architecture, connecting an SSH client application with an SSH server.
- The protocol specification distinguishes between two major versions, referred to as SSH-1 and SSH-2.
- The standard TCP port for SSH is 22.
- SSH is generally used to access Unix-like operating systems, but it can also be used on Microsoft Windows.
- Windows 10 uses OpenSSH as its default SSH client and SSH server.

## PuTTY
- A free and open-source terminal emulator, serial console and network file transfer application.
- It supports several network protocols, including SCP, SSH, Telnet, rlogin, and raw socket connection.
- It can also connect to a serial port.
- The name "PuTTY" has no definitive meaning, though "tty" is the name for a terminal in the Unix tradition, usually held to be short for Teletype.
- PuTTY was originally written for Microsoft Windows, but it has been ported to various other operating systems.

# Remote Desktop Protocol (RDP) for Remote Login
- A proprietary protocol developed by Microsoft which provides a user with a graphical interface to connect to another computer over a network connection.
- The user employs RDP client software for this purpose, while the other computer must run RDP server software.
- Used by IT administrators to remotely control computers over a network.
- RDP is a protocol that provides a graphical interface to another computer on a network.
- SCCM uses RDP to remotely install software on a computer.
- Remote Access Trojan (RAT) uses RDP to remotely control a computer.
- Can be also used by hackers to remotely control a computer.

## Remote Desktop Services Example
- Remote Desktop Services (RDS), known as Terminal Services in Windows Server 2008 and earlier, is one of the components of Microsoft Windows that allow a user to take control of a remote computer or virtual machine over a network connection.
- TeamViewer is a proprietary software application for remote control, desktop sharing, online meetings, web conferencing and file transfer between computers.
- TightVNC is a free remote control software package derived from the popular VNC software.
- VNC software is cross-platform, allowing remote control between different types of computer.
- VNC software is used to remotely control a computer.

--------------------

## Micosoft Remote Desktop
- Allows a user to connect to a remote computer and use it as if it were their local computer.
- Run on port 3389.
- If Remote Desktop is enabled, use Network Level Authentication (NLA) to secure the connection.

![img](https://i.imgur.com/Yfh1JqU.png)

# Summary
This document provides an in-depth overview of two types of remote access software: VNC software and Microsoft Remote Desktop. VNC software is a practical tool used to remotely control a computer, providing users with the ability to manage their systems from afar. This can be particularly useful in situations where direct physical access to the machine is not possible or practical.

On the other hand, Microsoft Remote Desktop is a powerful tool that allows a user to connect to a remote computer and use it as if it were their local machine. This software operates on port 3389, providing a dedicated pathway for remote access.

For enhanced security, especially when Remote Desktop is enabled, it's recommended to use Network Level Authentication (NLA). NLA is a security measure that adds an extra layer of protection to the remote connection, ensuring that unauthorized users cannot gain access to the system.

In conclusion, both VNC software and Microsoft Remote Desktop offer robust solutions for remote access to computers. They each have their unique features and use-cases, and the choice between them depends on the specific needs and circumstances of the user. The document concludes with a summary of these key points.