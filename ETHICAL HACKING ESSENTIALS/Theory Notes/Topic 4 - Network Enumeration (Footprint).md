# Topic 4 - Network Enumeration (Footprint)

# Table of Contents
- [Topic 4 - Network Enumeration (Footprint)](#topic-4---network-enumeration-footprint)
- [Table of Contents](#table-of-contents)
- [What is Network Enumeration (Footprint)?](#what-is-network-enumeration-footprint)
- [Stages of Penetration Testing](#stages-of-penetration-testing)
  - [OVERVIEW OF INFORMATION GATHERING](#overview-of-information-gathering)
  - [INFORMATION GATHERING](#information-gathering)
- [What is Footprinting?](#what-is-footprinting)
- [Advanced Web Search Techniques](#advanced-web-search-techniques)
- [Whois](#whois)
  - [Example of a Whois Output](#example-of-a-whois-output)
- [Using Email](#using-email)
- [Analyzing a Company Web Site](#analyzing-a-company-web-site)
- [Finding information about connnected devices](#finding-information-about-connnected-devices)
- [Using Domain Name Service (DNS)](#using-domain-name-service-dns)
  - [Dertermine company's primary DNS server](#dertermine-companys-primary-dns-server)
- [Other DNS whois tools](#other-dns-whois-tools)
- [Traceroute](#traceroute)
  - [Are port scanning legal?](#are-port-scanning-legal)



-------------------------
# What is Network Enumeration (Footprint)?

- Footprinting is the process of collecting as much information as possible about a target network, for identifying various ways to intrude into an organization’s network system.
- Using Web tools for Footprinting 
- Using DNS and DNS zone transfer for Footprinting
- Viewing information in HTTP
- Identifying the types of social engineering

-------------------------
# Stages of Penetration Testing
- Stage 1 : Information Gathering ( Footprinting )
  - Gather information about the target network, e.g. IP address, domain name, etc.
- Stage 2 : Network Discovery and Scanning
  - Scan the target network for open ports, services, and vulnerabilities.
- Stage 3 : Vulnerability Assessment
  - Identify the vulnerabilities in the target network, e.g. weak passwords, using outdated software, HTTP protocol, etc.
- Stage 4 : Exploitation
  - Exploit the vulnerabilities in the target network to gain access to the target system, e.g. using Metasploit.
- Stage 5 : Post Exploitation
  -   Maintain access to the target system, e.g. using backdoors, rootkits, etc. 
-------------------------

## OVERVIEW OF INFORMATION GATHERING
YouTube Link:
https://www.youtube.com/watch?v=vkOo0SymOaw

-------------------------

## INFORMATION GATHERING

- Numerous resources to find information about a target network legally
- Information gathering is the first step in the penetration testing process and find information about your organization
- Companies should try to limit the amount of information that is publicly available about their network

-------------------------

# What is Footprinting?
- Discovering information about
    - Computer systems
    - Network infrastructure
    - Organization
    - Employees
    - Physical security
    - Security posture

- Usually, such information is publicly available on the Internet, e.g. company website, social media (Facebook, Twitter, LinkedIn, etc.), etc.

- Information gathered may be used to determine how to conduct security test (for hackers, the information can be used to determine how to attack the target network) 
    - This can come down to 
      - Size of the organization
      - Size of the network
      - Operating systems used

- What are the infomation that you like to find out?
  - Domains
    - The target may own multiple domains (e.g. .com, .net, .org, etc.)

  - Visible systems
      - How many systems are visible to the Internet/Public? e.g. web servers, mail servers, etc.

  - Software Services available
    - What are the main public services provided? Test are generally conducted on these services ports like 21, 22, 23, 25, 80, 110, 139, 443, 445, etc.

  - IP Addresses Discovery
    - Knowing their IP addresses range will help you to determine the number of systems in the network
      - Eg. 192.168.1.0/28
        - Subnet: 16 Hosts: 14 hosts

  -  Getaway routers
       - Knowing the gateway router will help you to determine who is the ISP and the type of connection to the Internet
         - Eg. MyRepublic, Singtel, Starhub, etc.

    - Primary Operating System
      - Knowing the operating system will help you to determine the type of attacks to be conducted
        - Eg. Windows, Linux, etc.  

    - Firewall
      - Knowing the firewall will help you to determine the type of attacks to be conducted
        - Eg. Cisco, Juniper, etc.

    - Intrusion Detection System (IDS) / Intrusion Prevention System (IPS)
      - Knowing the IDS/IPS will help you to determine the type of attacks to be conducted
      - Is there one? Will it detect your attacks?
        - Eg. Snort, Suricata, etc.

    - Web Technologies
      - Knowing the web technologies will help you to determine the type of attacks to be conducted
      - Is there web site using Python, JavaScript, PHP, etc.?
      - Are they hosting their own web server or using a web hosting company?
        - Eg. Apache, IIS, etc.
        - Eg. GoDaddy, BlueHost, etc.

![img](https://i.imgur.com/GyomPkM.png)



# Advanced Web Search Techniques
- Google allows different types of search techniques to be used to narrow down the search results

Example:
- To find a certain phrase, enclose the phrase in double quotes
  - E.g. “ethical hacking”
  - E.g website: www.sp.edu.sg exams

To find certain file types, use the filetype: operator
  - E.g. filetype:pdf ethical hacking
  - E.g. filetype:pdf site:sp.edu.sg exams


- To find certain words in the title, use the intitle: operator
    - E.g. intitle:”ethical hacking”
    - E.g. intitle:”ethical hacking” site:sp.edu.sg

You can always use www.google.com/advanced_search to perform advanced search

https://www.google.com/advanced_search 

# Whois

- Domain names are registered with a NICs (Network Information Center)
  - E.g. InterNIC, APNIC, etc.

- Regional Internet Registries (RIRs) handles IP allocation 
  - American Registry for Internet Numbers (ARIN)
  - Asia-Pacific Network Information Centre (APNIC)

Who is Database allows querying on who owns the domain, contact information, IP address, etc.

## Example of a Whois Output
```bash
root@kali:~# nc whois.arin.net 43
18.7.22.69

OrgName:    Massachusetts Institute of Technology
OrgId:      MIT-2
Address:    77 Massachusetts Avenue
City:       Cambridge
StateProv:  MA
PostalCode: 02139
Country:    US

NetRange:   18.0.0.0 - 18.255.255.255
CIDR:       18.0.0.0/8
NetName:    MIT
NetHandle:  NET-18-0-0-0-1
Parent:     ()
NetType:    Direct Assignment
OriginAS:
NameServer: STRAWB.MIT.EDU
NameServer: W20NS.MIT.EDU
NameServer: BITSY.MIT.EDU
Comment:    ADDRESSES WITHIN THIS BLOCK ARE NON-PORTABLE
RegDate:    1985-08-30
Updated:    2015-09-28

TechHandle: ARB8-ARIN
TechName:   Borkowski, Adam Robert
TechPhone:  +1-617-253-1333
TechEmail:  jit@mit.com

OrgAbuseHandle: MITNO-ARIN
OrgAbuseName:   MIT Network Operations
OrgAbusePhone:  +1-617-253-8400
OrgAbuseEmail:  abuse@mit

# ARIN WHOIS database, last updated 2017-10-31 19:00
# Enter ? for additional hints on searching ARIN's WHOIS database.

root@kali:~#
```

# Using Email 
In the current industry this technique is unable to expose company’s employee organization email in public website, as there is a public email that would be used for general enquiries.


- Email address can help you retrive information about the target network
  
- Find e-mail address format
  - E.g. Guess other employees’ email addresses based on email accounts

- Bounce an email using a non-existent email address
  - E.g. bounce an email to a non-existent email address and see if the email bounces back
  - Read the email header
  - Get information about the email server

- Tool to find corporate email addresses
  - E.g. theHarvester, groups.google.com, etc.


# Analyzing a Company Web Site

- Web pages are an easy source of information
  - E.g. company’s products, services, contact information, etc.

- Simplest tool is browser
- View the source code of the web page
  - E.g. hidden comments, hidden links, etc.

```html
<html>
<head>
<title>ABC E-Commerce Website</title>
<!--Developed by DEF Web Developers Company -->
```
# Finding information about connnected devices

- Shodan is a search engine that lets the user find specific types of computers (web cams, routers, servers, etc.) connected to the Internet using a variety of filters
- https://www.shodan.io/


# Using Domain Name Service (DNS)
DNS
- Resolves domain names to IP addresses 
  - Instead of IP address it will be a domain name
- People perfers to remember domain names than IP addresses 
  - Imagine having to remember the IP address of every website you visit (e.g. google.com vs 150.150.0.0)
- Can be vulnerable to attacks
  - E.g. DNS spoofing, DNS cache poisoning, etc.

- DNS Query tools 
- nslookup
- dig
- host
- whois
- dnsenum
- dnsmap
- nmap
- Netcraft
- Netcat (banner grabbing)

## Dertermine company's primary DNS server
- Use nslookup to find out the primary DNS server
  - E.g. nslookup www.sp.edu.sg
  - E.g. nslookup -type=ns sp.edu.sg
- Look for the SOA (Start of Authority) record
  - E.g. nslookup -type=soa sp.edu.sg
- Shows the zone file for the domain

- Zone Transfers
  - Enables you to see all hosts on a network
  - Gives your organization's network diagram

# Other DNS whois tools
- www.whois.net
- greenwich
- Wikto
- SmartWhois    
- ActiveWhois
- SpiderFoot
- Maltego
- DNSenum

# Traceroute
- Why do we need to use TraceRoute?
  - To find out the path that the packet takes to reach the destination
  - To find out the number of hops to reach the destination
  - To find out the IP address of each hop

## Are port scanning legal?

Some countries have laws against port scanning

Read this article "Is Unauthorized Port Scanning Crime?"

https://nmap.org/book/legal-issues.html

Ensure you always have the permission to conduct port scanning

- Port scanning can generate a lot of traffic and may be detected by IDS/IPS, so narrow down the scan to specific ports 
  - e.g if you are looking for web servers, scan only port 80 and 443 instead of scanning all ports


