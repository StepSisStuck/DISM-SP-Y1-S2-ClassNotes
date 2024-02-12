# Topic 8A - System Security (Firewall)

# Table of Contents
- [Topic 8A - System Security (Firewall)](#topic-8a---system-security-firewall)
- [Table of Contents](#table-of-contents)
- [What is NAT (Network Address Translation)?](#what-is-nat-network-address-translation)
  - [Why do we use NAT?](#why-do-we-use-nat)
  - [How does NAT works?](#how-does-nat-works)
- [What is a proxy server?](#what-is-a-proxy-server)
  - [Advantages and Disadvantages on Proxy Servers](#advantages-and-disadvantages-on-proxy-servers)
    - [Choosing a Proxy Server](#choosing-a-proxy-server)
  - [Reverse Proxy Server](#reverse-proxy-server)
- [DMZ](#dmz)
- [Bastion Host](#bastion-host)
- [Honeypot](#honeypot)
- [Overview of Firewalls](#overview-of-firewalls)
  - [Firewall rules](#firewall-rules)
  - [Personal Firewall](#personal-firewall)
  - [Enterprise Firewall](#enterprise-firewall)
    - [But firewall is only part of the security solution](#but-firewall-is-only-part-of-the-security-solution)
  - [Packet Filtering Firewall](#packet-filtering-firewall)
    - [Stateless Packet Filtering Firewall](#stateless-packet-filtering-firewall)
    - [Stateful Packet Filtering Firewall](#stateful-packet-filtering-firewall)
- [Typical locations of Packet Filtering Firewalls](#typical-locations-of-packet-filtering-firewalls)
  - [Configuring Firewall Rules](#configuring-firewall-rules)
  - [Base firewall rules on security policy](#base-firewall-rules-on-security-policy)
  - [Keeping the rule base simple](#keeping-the-rule-base-simple)
  - [General Practices for Firewall Rules](#general-practices-for-firewall-rules)
  - [Anti-spoofing rule](#anti-spoofing-rule)
  - [Firewall Logging and Auditing](#firewall-logging-and-auditing)
  - [Comparing software and hardware firewalls](#comparing-software-and-hardware-firewalls)
    - [Software Firewall](#software-firewall)
    - [Hardware Firewall](#hardware-firewall)
    - [Hybrid Firewalls](#hybrid-firewalls)


--- 

# What is NAT (Network Address Translation)?

- A network device (usually a firewall, proxy server or router)
  - They hides internal IP addresses from the external IP address

But let's roll it back, what is a NAT?

- Imangine you have 100 devices you need ot connect by your company
  - Hundreds or even thousands can be behind a single public IP address
- Internal IP are also hidden from outside attackers

## Why do we use NAT?

- This helps reduces the number of public IP addresses required by an organisation
  - Hundreds or even thousands of internal computers can be behind a single public IP address


NAT (Network Address Translation) is used for several reasons:

1. **IP Address Conservation**: NAT allows private networks to use private IP addresses internally, while presenting a single public IP address or a small range of public IP addresses to the outside world. This helps conserve the limited number of public IP addresses available.

2. **Security**: By hiding the internal IP addresses, NAT adds a layer of privacy and security to the network, making it more difficult for attackers to discover and exploit internal network resources.

3. **Flexibility**: NAT allows a network to change its public IP address or even switch to a different ISP without needing to change the internal IP addresses.

4. **Ease of Administration**: If a network using NAT changes its internal IP scheme, it doesn't need to coordinate with the ISP or reconfigure the public interface.


## How does NAT works?

Network Address Translation (NAT) works by modifying the IP address information in packets while they are in transit. Here's a simplified step-by-step process:

1. A device from the internal network makes a request to a device on the internet. The source IP in the packet is the private IP of the internal device.

2. The packet reaches the NAT device (usually a router). The NAT device saves a mapping of the internal private IP and port to a public IP and port in a NAT table.

3. The NAT device changes the source IP in the packet to its public IP, and the source port to the mapped port. It then sends the packet to the internet.

4. When a response comes back from the internet, the NAT device uses the NAT table to determine where to forward the packet. It changes the destination IP in the packet to the internal private IP, and the destination port to the mapped port.

5. The packet is then sent to the correct internal device.

This process allows multiple devices to share a single public IP address, as each internal device will have a unique combination of private IP and port.

![img](https://i.imgur.com/n9tXKDu.png)


![img](https://i.imgur.com/jeoPNJT.png)

![img](https://i.imgur.com/bFMeDpp.png)

![img](https://i.imgur.com/n0d7c9T.png)

# What is a proxy server?

A proxy server is a server that acts as an intermediary for requests from clients seeking resources from other servers. When a client makes a request, the proxy server evaluates the request according to its filtering rules. If the request is validated by the filter, the proxy provides the resource by connecting to the relevant server and requesting the service on behalf of the client. 

Proxy servers provide various functionalities such as:

1. **Anonymity**: By hiding the client's IP address, a proxy server ensures that the destination server doesn't know who made the original request, which can provide anonymity to the user.

2. **Security and Privacy**: Proxy servers can provide security and privacy by blocking web content that may contain malware or by preventing websites from tracking the user's activities.

3. **Caching**: A proxy can cache (store a copy of) web content and deliver it quickly to users, which can help reduce bandwidth usage and speed up web access.

4. **Content Filtering**: Proxy servers can also be used to control access to websites or to block certain types of content.

- Proxy servers can also be used to hide IP addresses


![img](https://i.imgur.com/OCyPKFr.png)


![img](https://i.imgur.com/79bhKNe.png)



![img](https://i.imgur.com/eaRZvBa.png)


## Advantages and Disadvantages on Proxy Servers 
| Advantages | Disadvantages |
|------------|---------------|
| Anonymity: Proxy servers can hide your IP address, providing anonymity online. | Slower Speed: Since your requests are routed through another server, it can slow down your internet speed. |
| Security and Privacy: Proxy servers can provide an extra layer of security by blocking web content that may contain malware. | Complexity: Setting up and maintaining a proxy server can be complex and require technical knowledge. |
| Caching: Proxy servers can cache web content, which can speed up access to data you frequently use. | Privacy Concerns: If the proxy server is not properly configured or if it's operated by a malicious entity, it could potentially monitor your internet activity. |
| Content Filtering: Proxy servers can control access to certain types of web content. | Cost: While there are free proxies, they often have limitations or ads. Premium proxies can add an extra cost. |


### Choosing a Proxy Server

- Freeware Proxy Server
  - Often described as content filtering 
  - May not have advanced features
  - Example: Squid
- Commercial proxy servers
  - Offer Web page caching, source and destination IP addresses translation, content filtering, and NAT
  - Example: Many hardware firewalls come with proxy server functionality
  

## Reverse Proxy Server
A reverse proxy server is a type of proxy server that retrieves resources on behalf of a client from one or more servers. These resources are then returned to the client as though they originated from the proxy server itself. 

Unlike a forward proxy server which serves clients who are seeking resources from other servers, a reverse proxy server appears to the client just like an ordinary web server. 

Reverse proxies are used for several reasons:

1. **Load Balancing**: A reverse proxy can distribute client requests across multiple servers, thus balancing the load and ensuring no single server becomes overwhelmed.

2. **Increased Security**: By hiding the existence and characteristics of origin servers, a reverse proxy server provides an additional layer of security.

3. **SSL Termination**: The reverse proxy server can be used to handle SSL encryption/decryption, thus offloading this task from the web servers and freeing up resources.

4. **Caching**: Just like forward proxies, reverse proxies can also cache content, reducing the load on backend servers.


# DMZ 
DMZ stands for "Demilitarized Zone" in the context of network security. It refers to a physical or logical subnetwork that contains and exposes an organization's external-facing services to a larger and untrusted network, usually the internet. 

The purpose of a DMZ is to add an additional layer of security to an organization's local area network (LAN); an external attacker only has access to equipment in the DMZ, rather than any other part of the network. The DMZ functions as a small, isolated network positioned between the internet and the private network and, if configured correctly, can prevent attackers from gaining access to data stored on a network's servers. 

Services that are provided to users on the external network can be placed in the DMZ. Some examples of such services are: email, web, and DNS servers.


- But public users can access the DMZ servers but cannot enter the internal network
  - People would call this as service network or perimeter network

![img](https://i.imgur.com/tUrurHI.png)

# Bastion Host
- Normally refers to a computer that has been specially protected and hardened to resist attacks, through OS patches, authentication, and other security measures.
- Such special security measures are necessary because the bastion host is the only host that is exposed to the public network and is therefore the most vulnerable to attacks.
- Usually provides Web, FTP, and email services to the public network and is often used as a proxy server.

![img](https://i.imgur.com/oUIqZYa.png)

# Honeypot
A honeypot is a security mechanism set to detect, deflect, or counteract attempts at unauthorized use of information systems. Generally, a honeypot consists of data (for example, in a network site) that appears to be a legitimate part of the site, but is actually isolated and monitored, and that seems to contain information or a resource of value to attackers, which are then blocked and reported.

- They can learn about the attackers and their methods
- Attracts attackers away from the real servers

- Legal issues: Honeypots can be used to collect information about attackers, but there are legal and ethical issues to consider. For example, if an attacker is lured into a honeypot and then attacked, the honeypot owner could be held liable for the attack. It's important to consult with legal experts before deploying a honeypot.
![img](https://i.imgur.com/ydIz2YO.png)

# Overview of Firewalls
- Firewalls are used to protect a network from unauthorized access
  - They can be hardware or software based
  - To block unauthorized access, they use a set of rules to filter traffic
- Earliest firewalls were packet filters
  - They examine the header of each packet and decide whether to allow or block it
  - Explaination: A packet filter firewall examines the header of each packet and decides whether to allow or block it based on a set of rules. The rules can be based on the source and destination IP address, port numbers, and other packet header fields. Packet filter firewalls are fast and efficient, but they can't inspect the contents of the packet, so they can't block attacks that are hidden within the packet payload.

## Firewall rules 
- They can be configured by setting rules
  - Rules can be based on IP addresses, port numbers, and other packet header fields
  - They can be configured to allow or block traffic based on the rules
- Rules for blocking traffic can be done on case by case basis
  - For example, you can block traffic from a specific IP address or a range of IP addresses
    - Action includes:
      - Allow the traffic
      - Deny the traffic
      - Customized access (e.g. allow traffic from a specific IP address)

![img](https://i.imgur.com/u7EVydj.png)


## Personal Firewall
- Personal firewalls are software-based firewalls that run on individual computers
  - They are used to protect the computer from unauthorized access
  - They can be used to block or allow traffic based on a set of rules

## Enterprise Firewall
- Enterprise firewalls are hardware or software-based firewalls that are used to protect an entire network
  - They can be used to block or allow traffic based on a set of rules
  - They can be used to protect the network from unauthorized access

### But firewall is only part of the security solution
- Firewall are not only a standalone security solution
  - They are part of a larger security solution
  - They are used in conjunction with other security measures such as antivirus software, intrusion detection systems, and encryption

- They can be combined with other security measures such as 
  - Antivirus software
  - Intrusion detection systems
  - Encryption
  - VPNs
  - Authentication systems

## Packet Filtering Firewall
- They only check the infomation in the packet header
  - They can't inspect the contents of the packet
  - They can't block attacks that are hidden within the packet payload
- Stateless packet filtering firewalls
  - They examine each packet in isolation
  - They don't keep track of the state of the connection
  - They can't detect if a packet is part of an established connection or a new connection
- Stateful packet filtering firewalls
  - They keep track of the state of the connection
  - They can detect if a packet is part of an established connection or a new connection
  - They can make more intelligent decisions about whether to allow or block traffic

### Stateless Packet Filtering Firewall
- They decide whether to allow or block traffic based on the packet header
  - They don't keep track of the state of the connection
  - They can't detect if a packet is part of an established connection or a new connection

- Filtering based on common IP header features
  - IP address and Ports 
  - Protocol
  - Flags and options

- Advantage: Inexpensive and fast
- Disadvantage: They can't inspect the contents of the packet, so they can't block attacks that are hidden within the packet payload. Attacks are more complex and can be hidden within the packet payload
  
| Rule | Source IP | Destination IP | Source Port | Destination Port | Protocol | Action |
|------|-----------|----------------|-------------|------------------|----------|--------|
| 1    | Any       | Any            | Any         | 80               | TCP      | Allow  |
| 2    | Any       | Any            | Any         | 443              | TCP      | Allow  |
| 3    | 192.0.2.0 | Any            | Any         | Any              | ICMP     | Allow  |
| 4    | Any       | Any            | Any         | Any              | Any      | Deny   |

### Stateful Packet Filtering Firewall
 Besides looking at information in the protocol headers, keeps a record of connections the host computer has made with other computers. This allows the firewall to make decisions based on the context of the traffic, rather than just the individual packets.


 - This maintains a state table that keeps track of the state of the connection
   - It can detect if a packet is part of an established connection or a new connection
   - It can make more intelligent decisions about whether to allow or block traffic
 - It also allows incoming packets to pass through only from external host already connected to the internal host


![img](https://i.imgur.com/Y21lGwF.png)


# Typical locations of Packet Filtering Firewalls
- Between the internal network and the internet
  - They can be used to protect the internal network from unauthorized access
- Between a proxy server and the internet
  - They can be used to protect the proxy server from unauthorized access
- At either end of a DMZ
  - They can be used to protect the DMZ from unauthorized access


## Configuring Firewall Rules

- Rule base
  - Tells firewalls what to do when a certain condition is met to a packet
    - Rules can be based on IP addresses, port numbers, and other packet header fields
- Points to consider
  - Based on organization's security policy
  - Determine what can be acccessed from external network
  - Logging and auditing requirements
  - Regular review of rules
  - Network Address Translation (NAT) rules
  - Simple and short rules are easier to manage - firewall should not cause too much delay in network speed, and should not be too complex to manage

## Base firewall rules on security policy 
- The rules should be based on the organization's security policy
  - The security policy should define what can be accessed from the external network
  - The rules should be based on the security policy
  - The rules should be reviewed regularly to ensure that they are still relevant

- Example of this:
  - Employees have access to the internet but with restrictions
  - Public users have access to the web server but not to the internal network
  - Only authorized users have access to the internal network
  - Employees are not allowed to use instant messaging or peer-to-peer file sharing applications
  - Traffic from the company's ISP should be allowed 
  - Only network administrators should have access to the firewall



## Keeping the rule base simple


1. **Keep the list of rules as short as possible**: The fewer rules to process, the faster the firewall can make a decision. 

2. **Order of rules matters**: Firewalls process rules in a specific order, usually from top to bottom. If a packet matches a rule, the firewall will apply that rule and stop processing further. 

3. **Place important and frequently accessed rules at the top**: Since the firewall processes rules from top to bottom, placing the most frequently accessed rules at the top can speed up the decision-making process.

4. **Use a cleanup rule as the last rule**: This is a catch-all type of rule that applies if none of the previous rules match. It's usually set to deny all, ensuring that only traffic matching the above rules is allowed. 

Here's an example of a simplified stateless packet-filtering rules table following these guidelines:


| Rule | Source IP | Destination IP | Source Port | Destination Port | Protocol | Action |
|------|-----------|----------------|-------------|------------------|----------|--------|
| 1    | Any       | Any            | Any         | 80               | TCP      | Allow  |
| 2    | Any       | Any            | Any         | 443              | TCP      | Allow  |
| 3    | Any       | Any            | Any         | Any              | Any      | Deny   |


In this table, HTTP (port 80) and HTTPS (port 443) traffic are allowed from any source. All other traffic is denied by the cleanup rule.



## General Practices for Firewall Rules
- Rules should follow a few general practices
  - Most frequently accessed rules should be placed at the top
  - Nobody can access the firewall except the network administrators
  - Block direct access to the internal network from the internet
  - Permit access to public servers from the internet


## Anti-spoofing rule

- In many firewall configuration, the first rule is the Anti-spoofing rule.
- The anti-spooofing rule is used to prevent IP spoofing
  - IP spoofing is a technique used by attackers to gain unauthorized access to a network
  - It involves an attacker sending packets with a source IP address that is not their own
  - The anti-spoofing rule is used to block packets with a source IP address that is not valid for the network

![img](https://i.imgur.com/nIgk86Z.png)


## Firewall Logging and Auditing
- Decide what to log 
  - Some firewall can log all traffic, or maybe only the traffic that is denied (Blocked IP)
- Configuring the log file format
  - Many firewalls allow you to configure the format of the log file in plain text, or in a format that can be read by a log analysis tool
  - Sophisticated firewalls save log files in other formats such as XML or SQL
- Review logs files regularly 
- Log files can indicate signatures of attacks
  - For example, a large number of failed login attempts from a single IP address could indicate a brute force attack

  - Preparing log files summary
    - Log files can be used to prepare a summary of the traffic that has been allowed and denied
- Some firewall tools can contain log analysis tools
  - They can be used to analyze the log files and generate reports

## Comparing software and hardware firewalls

| Software Firewall | Hardware Firewall |
|-------------------|-------------------|
| Installed on individual computers | Installed on a dedicated device |
| Protects individual computers | Protects an entire network |
| Can be used to protect a single computer or a small network | Can be used to protect a large network |
| Can be used to protect computers that are not connected to a network | Can be used to protect a network that is connected to the internet |


- Hybrid firewalls
  - They combine the features of both software and hardware firewalls
  - They can be used to protect a network from unauthorized access
  - They can be used to protect individual computers from unauthorized access

### Software Firewall
- A software firewall is a firewall that is installed on individual computers
  - It is used to protect the computer from unauthorized access
  - It can be used to protect a single computer or a small network
  - It can be used to protect computers that are not connected to a network
- Some of them are free and some are paid
  - Example: Windows Firewall, ZoneAlarm, Comodo Firewall
- Some of them are also capable of managing muilple computers
  - Example: Windows Firewall can be managed through Group Policy

| Pros and Cons | Description |
|---------------|-------------|
| **Pros**      |             |
| Cost Effective | Software firewalls are generally less expensive than hardware firewalls. Some are even available for free. |
| Flexibility | They can be easily updated or reconfigured as they are software-based. |
| Customizable | They often offer more advanced features and greater customization options compared to hardware firewalls. |
| **Cons**      |             |
| Resource Consumption | Software firewalls use system resources (CPU, memory) of the host machine, which can impact performance. |
| Vulnerability | They are installed on the system they protect, so if the system is compromised, the firewall could be too. |
| Complexity | They can be complex to set up and manage, often requiring a good understanding of network protocols and applications. |


### Hardware Firewall
- A hardware firewall is a firewall that is installed on a dedicated device
  - It is used to protect an entire network from unauthorized access
  - It can be used to protect a large network
  - It can be used to protect a network that is connected to the internet
  
| Pros and Cons | Description |
|---------------|-------------|
| **Pros**      |             |
| Dedicated Resources | Hardware firewalls have their own dedicated resources and do not consume system resources of the network's computers. |
| High Performance | They are designed to handle a large amount of network traffic without slowing down the network. |
| Security | They provide a high level of security and can protect the entire network by being positioned at the network's edge. |
| **Cons**      |             |
| Cost | Hardware firewalls can be expensive to purchase and maintain. |
| Complexity | They can be complex to set up and manage, often requiring specialized knowledge. |
| Physical Space | They require physical space and proper environmental conditions to operate. |


### Hybrid Firewalls
- A hybrid firewall is a firewall that combines the features of both software and hardware firewalls
  - It can be used to protect a network from unauthorized access
  - It can be used to protect individual computers from unauthorized access
  - It can be used to protect a network that is connected to the internet

| Pros and Cons | Description |
|---------------|-------------|
| **Pros**      |             |
| Enhanced Security | Hybrid firewalls provide the benefits of both hardware and software firewalls, offering enhanced security. |
| Flexibility | They offer the flexibility of software firewalls with the dedicated resources of hardware firewalls. |
| Scalability | They can be easily scaled to accommodate network growth. |
| **Cons**      |             |
| Cost | Hybrid firewalls can be more expensive than either hardware or software firewalls alone. |
| Complexity | They can be complex to set up and manage, often requiring specialized knowledge. |
| Maintenance | They require maintenance of both hardware and software components. |
