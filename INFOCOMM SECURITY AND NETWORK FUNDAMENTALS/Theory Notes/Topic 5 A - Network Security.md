# Network Security

Table of Contents


# Attacks on networks
- Threat actors place a high priority on targeting networks in their attacks.
- Exploit a single network vulnerability can expose hunreds or thousands of systems to attack.
- Attacks that target a network or a process that relies on a network include:
  - Interception Attacks
  - Layer 2 Attacks
  - DNS Attacks
  - Distributed denial of Service Attacks (DDOS Attacks)
  - Malicious Codding and Scripting attacks

## Interception Attacks
- Interception attacks are attacks that capture data as it travels over a network.

### Examnple of Interception Attacks
#### Man-in-the-middle attack (MITM)
  - In an MITM, a threat actor is positioned in a communication between two parties.
  - The goal of the attack is to intercept and alter the communication, example: ease dropping or impersonation of one of the parties.
  - Application used: Wireshark, Ettercap, Cain and Abel, and SSLStrip.

- A typical MITM attact have two phases:
  - The first phase is to intercept the communication.
  - The second phase is to decrypt the communication.'

![img](https://i.imgur.com/lBoWpbf.png)


#### Session Replay

- A replay attack makes a copy of a legitimate transmission and then replays it to the recipient.
- Attacker uses the copy at a later time to impersonate the sender.
- Example: capture a user's authentication credentials and then replay them to gain access to a system.


- Threat actors use several techniques for stealing an active session ID:
  - Network attacks (Hijacks and altered communcation between two parties)
  - Endpoint attacks (Malware, keyloggers, cross-site scripting, Trojans, and other malicious code (JavaScript Coding))


#### Man-in-the-browser attack (MITB)

- MITB is a form of MITM attack that infects the browser rather than the computer.
- A MITB attack intercepts and alters the communication between a user and a website to steal and manipulate the data being exchanged.
  - Example: A threat actor can use a MITB attack to change the account number and routing number on a bank transfer request.
- MITB attacks are difficult to detect because they occur within the browser and not on the computer or the network.
  - It occurs within the browser and not on the computer or the network.
  
  
- A MITB attack usually begins with Trojan infecting the computer and installing an "extention" into the browser configuration.
  - When the browser is launched, the extension is loaded and the attack begins.
  - Extentions wait for the user to visit a specific website, such as a banking site.
  - When user click "Submit" or "Transfer", the extension intercepts the request and alters the data, or they captures all the data from the form and sends it to the attacker.

##### Advantages of a MITB attack

- Most MITB attacks are distrubte through malware (Trojans) extensions making it difficult to detect by the antivirus software.
- An infected computer can be used to attack multiple websites and they might remain dormant for a long time before they are activated (Triggered by a specific event).

- MITB software resides exclusively on the infected computer and does not require any changes to the network or the website.


## Layer 2 Attacks
- The OSI reference model is divided into seven layers.

Layer | Name | Description
--- | --- | ---
1 | Physical | Defines the physical characteristics of the network, such as the medium, the connectors, and the signaling.
2 | Data Link | Defines the format of the data on the network.
3 | Network | Defines the format of the data on the network.
4 | Transport | Defines the format of the data on the network.
5 | Session | Defines the format of the data on the network.
6 | Presentation | Defines the format of the data on the network.
7 | Application | Defines the format of the data on the network.

- Within each layer, different networking tasks are performed that cooperate with the tasks in the layer immediately above and below it.
- Layer 2 the Data Link layer is divided into two sublayers:
  - Logical Link Control (LLC)
  - Media Access Control (MAC)
    - A compromise at Layer 2 can affect the entire communication process.

### Address Resolution Protocol Poisoning (ARP Poisoning)
  - ARP poisoning is an attack that exploits the way that the Address Resolution Protocol (ARP) works.
  - ARP is a protocol that is used to map IP addresses to MAC addresses.
  - ARP poisoning is also known as ARP spoofing.


### Media Access Control Attacks
- Other attacks manipulate the MAC address of a device.
- Two common attacks involving spoofing MAC addresses are:
  - MAC flooding
  - MAC cloning
- In a **MAC cloning attack**, the attacker captures a legitimate MAC address from a network and then changes the MAC address of their own device to match the legitimate MAC address.
  - They spoof the MAC address on and the writch changes its MAC address table to reflect the MAC address with the port to which the attacker's device is connected.
- A **MAC flooding attack** is another attack baised on spoofing, MAC cloning, and MAC address table of a switch
  - A threat actor overflows the switch with Ethernet packets that have been spoofed so that every packet contains a different source MAC address.

## DNS Attacks
- Domain Name System (DNS) is a service that translates domain names to IP addresses.
  - A DNS-based attack subverts the DNS resolution process to another server that is controlled by the attacker.
  - The attacker can then redirect the user to a malicious website or to a fake website that is designed to look like a legitimate website.
  - A successful DNS attack can be used to redirect users to a malicious website that is designed to look like a legitimate website and they have 2 consequences:
    - URL redirection
    - Domain reputation
  - Attacks using DNS include DNS poisoning, DNS spoofing, and DNS hijacking.

### DNS poisoning
- DNS poisoning is a technique that replaces a legitimate IP address with a rogue IP address.
- Two locations for DNS poisoning:
  - Local Host Table
  - External DNS Server



### DNS Hijacking
- DNS hijacking is a technique that redirects a user to a malicious website.
- DNS hijacking is intended to infect an external DNS server with IP address that point to malicious websites.
- DNS hijacking has an advantage of redirecting multiple users to a malicious website without having to infect each user's computer.
- Attackers attempt to exploit a protocol flaw convince the authentic DNS server to accept the malicious IP address.
- If the DNS server does not correctly validate the IP address, it will accept the malicious IP address and cache it.
   - This spreads them to other DNS servers that query the authentic DNS server.

![img](https://i.imgur.com/KHNcu45.png)


## Malicious Coding and Scripting Attacks
- Malicious coding and scripting attacks are attacks that use malicious code to exploit vulnerabilities in software.
- Some network attacks come from malicious code that is executed on a user's computer.
- These attacks use PowerShell, JavaScript, and coding languages such as C, C++, and Java.
- PowerShell is a scripting language that is used to automate administrative tasks, and they are configuation management framework from Microsoft 
- 

