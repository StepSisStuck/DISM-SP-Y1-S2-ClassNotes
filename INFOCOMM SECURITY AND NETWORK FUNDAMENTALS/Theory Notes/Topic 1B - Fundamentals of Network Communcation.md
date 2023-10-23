# Topic 1B The Fundermental of Network Communication

# Table of Contents

- [Topic 1B The Fundermental of Network Communication](#topic-1b-the-fundermental-of-network-communication)
- [Table of Contents](#table-of-contents)
- [Network Components](#network-components)
- [Steps of Network Communication](#steps-of-network-communication)
- [Layers of Networking Communication Process](#layers-of-networking-communication-process)
- [How Two Computers Communicate Local Area Network (LAN)](#how-two-computers-communicate-local-area-network-lan)
- [LANs, Internetworks, MANs, WANs](#lans-internetworks-mans-wans)
- [Internet, Intranet, Extranet](#internet-intranet-extranet)
- [Packets and Frames](#packets-and-frames)
- [Client and Server](#client-and-server)
  - [Client](#client)
  - [Server](#server)
- [Network Models](#network-models)
  - [Network models fall into two categories:](#network-models-fall-into-two-categories)
  - [Peer-to-peer network/Workgroup Model](#peer-to-peer-networkworkgroup-model)
    - [Issues with Peer-to-peer network/Workgroup Model](#issues-with-peer-to-peer-networkworkgroup-model)
  - [Server-based network/Domain Model](#server-based-networkdomain-model)
- [Summary](#summary)


-----------------

# Network Components 
- Hardware components needed to turn on a stand-alone computer into a networked computer
- Network Interface Card (NIC) Plug-in card that connects a computer to a network
- Network Media (Cable) - Connects the NIC to the network
- Network Operating System (NOS) - Software that allows a computer to communicate over a network

- Interconnection Devices - Connects multiple computers together on a network
- Hub - Connects multiple computers together on a network

# Steps of Network Communication

1. Application tries to access a network resource
2. Client software formats the request
3. Protocol stacks format the request into packets
4. NIC sends the packets onto the network
5. Packets are routed to the destination

- These are the same steps that occur when a computer accesses a resource on the Internet

# Layers of Networking Communication Process
![img](https://i.imgur.com/m5adNNi.png)

|Step|Layer|Description|
|----|-----|-----------|
|1|Application|The application layer is the layer that the user interacts with. It is the layer that the user sees.|
|2|Presentation|The presentation layer is responsible for formatting the data so that it can be read by the application layer.|
|3|Session|The session layer is responsible for establishing, maintaining, and terminating connections between applications.|
|4|Transport|The transport layer is responsible for breaking the data into segments and reassembling it at the destination.|
|5|Network|The network layer is responsible for addressing and routing the data between applications.|
|6|Data Link|The data link layer is responsible for formatting the data into frames so that it can be read by the network layer.|
|7|Physical|The physical layer is responsible for converting the data into bits so that it can be transmitted over the network.|

# How Two Computers Communicate Local Area Network (LAN)
- TCP/IP is the protocol suite used on the Internet
- TCP/IP uses 2 addresses to identify a computer on a network
- IP Address - Logical address that identifies a computer on a network
- MAC Address - Physical address that identifies a computer on a network

- Just as a mailing person needs a street address and a name to deliver a letter, a computer needs an IP address and a MAC address to deliver a packet
- Think of the Logical Address as the street address and the Physical Address as the name
- The IP address is the logical address that identifies a computer on a network

1. A user at Computer A types in the IP address of Computer B (Example: 10.1.1.2)
2. Network Interface Card (NIC) at Computer A sends out an ARP request to find the MAC address of Computer B
3. The Network Protocol Stack at Computer A formats the data into packets
4. The NIC at Computer A sends the packets onto the network
5. The network interface software adds the MAC address of Computer A to the packet
6. Computer B receives the packets and strips off the MAC address
7. The network protocol stack at Computer B reassembles the packets into data
8. The data is sent to the application

![img](https://i.imgur.com/eZQEP8c.png)

# LANs, Internetworks, MANs, WANs
- LAN (Local Area Network) - A network that connects computers in a limited geographical area
- An **Internetwork** is a network collections of LANs tied together by devices called routers
- Reasons for creation
    - Two or more groups of users need to share resources
    - Number of users and/or resources is too large for a single LAN
    - The distance between two groups of computer 
![img](https://i.imgur.com/Gw6hSRx.png)
![img](https://i.imgur.com/pJd6Ize.png)

- Wide Area Network (WAN) - A network that connects computers over a large geographical area
- Metropolitan area network (MAN) - A network that connects computers in a metropolitan area
- Campus Area Network (CAN) - A network that connects computers in a limited geographical area, such as a college campus

![img](https://i.imgur.com/SWmefCT.png)

# Internet, Intranet, Extranet

- The Internet is a worldwide collection of networks that connects millions of businesses, government agencies, educational institutions, and individuals
- The Internet is a public network

- An Extranet is a private network that uses Internet technologies to share business information with select corporate partners or key customers

- An Intranet is a private network that uses Internet technologies to share company information among employees

# Packets and Frames

- Computers transmit data in the form of packets
- information is broken into small pieces called packets
- Reasons for data to be broken into packets
    - Packets can travel different routes to the destination
    - Packets can be reassembled at the destination
    - Packets can be sent at the same time
    - Packets can be sent to multiple destinations

# Client and Server

## Client
- A **client** is a computer that requests data stored on a server

- The word client is used in these ways:

    - _Client operating system_ - A client operating system is an operating system that resides on a client computer
    - _Client software_ - Client software is software that requests data from a server
    - _Client computer_ - A client computer is a computer that requests data from a server

## Server
  
- A **server** is a computer that stores data that is requested by a client

- The word server is used in these ways:

    - _Server operating system_ - A server operating system is an operating system that resides on a server computer
    - _Server software_ - Server software is software that stores data that is requested by a client
    - _Server computer_ - A server computer is a computer that stores data that is requested by a client

# Network Models

- A network model is a set of standards for network communication that defines how data is sent and received
- The two most common network models are the Open Systems Interconnection (OSI) model and the TCP/IP model
- The OSI model is a theoretical model that describes how data should be transmitted between any two points in a telecommunication network
- The TCP/IP model is a practical model that describes how data is transmitted between any two points in a telecommunication network

## Network models fall into two categories:

- _Peer-to-peer_ - A peer-to-peer network is a network in which each computer can act as a client or a server for the other computers on the network
- _Server-based_ - A server-based network is a network in which one or more computers act as a server for the other computers on the network

## Peer-to-peer network/Workgroup Model 

- Computers on a peer-to-peer network can take on the role of either a **client or a server**
- Any user can share resources on his or her computer with other users on the network
- Every user is responsible for the security of his or her own computer
- They must be able to share resources with other users on the network / permission to access resources on other computers on the network
   - Can give everyone permission to access resources on their computer
   - Usernames and Password (credentials) are stored on each computer and to control access to resources

### Issues with Peer-to-peer network/Workgroup Model
- No centralized administration
- No centralized security
- No centralized storage
- No centralized backup
- No centralized software installation
- No centralized Internet access
- No centralized printer management
- No centralized user management
- No centralized resource management

- They must also remember the usernames and passwords for each computer on the network instead of just one username and password for the network like a server-based network / or a SSO Service (Single Sign On)

- Desktop PCs or Devices installed OS (Windows 11) aren't designed to be servers unlike dedicated servers OS like Windows Server 2019
- Data stored on desktop PCs or Devices are not as secure as data stored on servers and how can we keep track of the data stored on each desktop PCs or Devices

## Server-based network/Domain Model
- Server-based networks allows more control over the network resources
- Users log on to the network with a single username and password and can be accessed from more than one computer (Presuming the user has the permission to access the resources) / SSO Service (Single Sign On)
- Most of the OS on the dedicated servers are designed to be servers (Windows Server 2023/Oracle Linux Server)
- A domain is a logical group of computers that share a centralized directory database and they are managed by Windows Servers called **Domain Controllers**
- Users and Computers are managed by the Domain Controllers with the help of **Active Directory** (AD) which is a centralized database that stores information about the network resources and the users who access those resources
    - They can enforce security policies on the network
    - The software that manages this security is called **Group Policy**/**Group Policy Object** (GPO)/**directory service**
    - On Windows Server, the directory service is called **Active Directory** (AD)
    - On Linux Server, the directory service is called **OpenLDAP** (Lightweight Directory Access Protocol)
    - On Mac Server, the directory service is called **Open Directory** (OD)
    - On Oracle Linux Server, the directory service is called **389 Directory Server** (389DS)

- Other networks services found on network servers:
  - **File and Print Services** - Allows users to share files and printers on the network
  - **Web Services** - Allows users to access web pages on the network
  - **Email Services** - Allows users to send and receive email on the network
  - **Database Services** - Allows users to access databases on the network
  - **Application Services** - Allows users to access applications on the network
  - **Remote Access Services** - Allows users to access the network remotely
  - **Network Security Services** - Allows users to access the network securely

- Server-based networks are more secure than peer-to-peer networks because:
   - Users can be authenticated by the server
   - Users can be authorized to access resources on the network
   - Users can be audited to see what resources they have accessed
   - Data can be backed up centrally
   - Security policies can be enforced centrally
   - Software can be installed centrally using Software Deployment Tools like SCCM (System Center Configuration Manager) or Intune (Microsoft Endpoint Manager)
  
- Server-based networks are easier to expand then peer-to-peer networks because:
   - New users can be added to the network easily
   - New computers can be added to the network easily
   - New network services can be added to the network easily
   - Peer-to-peer networks are limited to 10 computers
   - Server-based networks can have thousands of computers/users

- Muiltiple servers can be configured to work together to provide the same service to the network
   - This is called **Load Balancing** and it is used to improve the performance of the network
   - If one server fails, the other servers can take over the load
     - This is called **Fault Tolerance** and it is used to improve the reliability of the network, if one server fails, the other servers can take over the load
     - This is called **High Availability** and it is used to improve the reliability of the network, high availability is a combination of load balancing and fault tolerance
     - This is called **Redundancy** and it is used to improve the reliability of the network, if one server fails, the other servers can take over the load

|Network Attribute|Peer-to-peer Network|Server-based Network|
|-----------------|--------------------|--------------------|
|Resoruce Access|Each user is responsible for the security of his or her own computer|Users can be authenticated, authorized, and audited|
|Data Storage|Data is stored on each computer|Data can be stored centrally|
|Network Management|No centralized management|Centralized management|
|Network Security|No centralized security|Centralized security|
|Network Expansion|Limited to 10 computers|Can have thousands of computers|

![img](https://i.imgur.com/dGgOkZT.png)

# Summary
This document provides an in-depth exploration of network communication fundamentals. It starts with an explanation of the necessary hardware components for creating a networked computer, including the Network Interface Card (NIC), Network Media, Network Operating System (NOS), and Interconnection Devices.

The process of network communication is then outlined, detailing each step from the initial application request to the routing of packets to their destination.

The document further breaks down the layers of the networking communication process, explaining the role and function of each layer from the application to the physical layer.

The method of communication between two computers over a Local Area Network (LAN) is discussed, with emphasis on the use of TCP/IP, IP Addresses, and MAC Addresses.

Various types of networks are examined, including LANs, Internetworks, MANs, WANs, and the broader categories of the Internet, Intranet, and Extranet.

The concept of data transmission via packets is introduced, followed by a detailed explanation of the client-server model.

The document concludes with a discussion on network models, specifically comparing and contrasting peer-to-peer and server-based networks, their characteristics, advantages, and disadvantages.

