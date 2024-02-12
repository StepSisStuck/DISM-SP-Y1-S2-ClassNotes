# Topic 8B - IDS and IPS

# Table of Contents
- [Topic 8B - IDS and IPS](#topic-8b---ids-and-ips)
- [Table of Contents](#table-of-contents)
- [What is a IDS (Intrusion Detection System)?](#what-is-a-ids-intrusion-detection-system)
- [What is a IPS (Intrusion Prevention System)?](#what-is-a-ips-intrusion-prevention-system)
- [IDS vs IPS](#ids-vs-ips)
- [Examining Intrusion Detection System Components](#examining-intrusion-detection-system-components)
  - [Sensors](#sensors)
    - [Network-based Sensors](#network-based-sensors)
    - [Host-based Sensors](#host-based-sensors)
    - [Ways of collecting network data](#ways-of-collecting-network-data)
    - [Collecting Data](#collecting-data)
    - [Network Sensors](#network-sensors)
    - [Sensor Deployment Concerns](#sensor-deployment-concerns)
  - [Alerting System](#alerting-system)
  - [Anomaly Detection (Profile-based Detection)](#anomaly-detection-profile-based-detection)
- [Some Definitions](#some-definitions)
  - [Misuse or attack signature Detection (rule-based Detection)](#misuse-or-attack-signature-detection-rule-based-detection)
- [Target Monitoring](#target-monitoring)
- [Data Correlation](#data-correlation)
- [Console](#console)
- [Response System](#response-system)
  - [Database of Attack Signatures or Behavior Profiles](#database-of-attack-signatures-or-behavior-profiles)
  - [Signature-based Detection](#signature-based-detection)
  - [Anomaly-based Detection](#anomaly-based-detection)
- [Examining Intrusion Prevention System Components Step by Step](#examining-intrusion-prevention-system-components-step-by-step)
  - [Step 1: Installing IDS Database](#step-1-installing-ids-database)
    - [Anomaly based detection](#anomaly-based-detection-1)
    - [Signature based detection](#signature-based-detection-1)
  - [Step 2: Gathering Data](#step-2-gathering-data)
  - [Step 3: Sending Alert Messages](#step-3-sending-alert-messages)
  - [Step 4: The IDS Response System](#step-4-the-ids-response-system)
  - [Step 5: The Administrator Accesses the Damage Through the Console](#step-5-the-administrator-accesses-the-damage-through-the-console)
  - [Step 6: Following Escalation Procedures](#step-6-following-escalation-procedures)
  - [Step 7: Logging and Reporting the Incident](#step-7-logging-and-reporting-the-incident)
- [Types of IDS](#types-of-ids)
- [Network-based intrusion detection system (NIDS)](#network-based-intrusion-detection-system-nids)
- [Freeware NIDS: Snort](#freeware-nids-snort)
- [Developing IDS filter rules](#developing-ids-filter-rules)
- [Rule Actions](#rule-actions)
  - [Snort](#snort)
- [Host-Based Intrusion Detection System (HIDS)](#host-based-intrusion-detection-system-hids)
  - [HIDS configuration](#hids-configuration)
- [Hybrid IDS Implementation](#hybrid-ids-implementation)
- [IDS Hardware Appliances](#ids-hardware-appliances)
- [HIDS](#hids)
- [Developing a Security Incident Response Team (SIRT)](#developing-a-security-incident-response-team-sirt)

--- 
# What is a IDS (Intrusion Detection System)?
- A system that monitors network traffic for suspicious activity and issues alerts when such activity is discovered.
- It is a passive system, meaning it does not take any action to prevent the attack.
- It is a monitoring system that is used to monitor the network traffic and system activity for any malicious activity or violation of the security policy.

# What is a IPS (Intrusion Prevention System)?
- A system that monitors network traffic for suspicious activity and can react to it.
- It is an active system, meaning it can take action to prevent the attack.
- It is a monitoring system that is used to monitor the network traffic and system activity for any malicious activity or violation of the security policy.

# IDS vs IPS
1

| Feature | IDS (Intrusion Detection System) | IPS (Intrusion Prevention System) |
|---------|---------------------------------|-----------------------------------|
| Purpose | Detect and alert on suspicious activity | Detect suspicious activity and take action to stop it |
| Action upon detection | Alerts the system or network administrator | Blocks or prevents the suspicious activity |
| Placement | Typically placed out of the direct flow of network traffic | Typically placed directly in the flow of network traffic |
| Impact on network performance | Usually minimal, as it just monitors and analyzes | Can potentially impact network performance due to active blocking |
| Complexity | Less complex as it only needs to detect and alert | More complex due to the need to take action upon detection |


![img](https://i.imgur.com/gkTpWNz.png)


# Examining Intrusion Detection System Components
- Typical Components of an IDS:
    - Sensors: Collect data from the network and systems.
    - Alerting System: Generates alerts based on the data collected by the sensors.
    - Console: Provides a user interface for the system administrator to manage the IDS.
    - Response System: Takes action based on the alerts generated by the alerting system.
    - Database of Attack Signatures: Contains a database of known attack signatures that the IDS uses to detect attacks.

## Sensors
- Electronic "eyes and ears" of the IDS.
- Hardware or software that monitors network traffic and system activity.
- Logs monitored data and sends it to the alerting system for analysis.

### Network-based Sensors
- Hardware or software that monitors network traffic.

This typically refers to a type of Intrusion Detection System (IDS) or Intrusion Prevention System (IPS) that is designed to monitor and analyze network traffic for any suspicious activity or threats. These systems are usually placed at a strategic point within the network to monitor inbound and outbound traffic to all devices on the network. They can detect malicious activities such as attacks or intrusions and can often take action to mitigate the threat, either by alerting administrators or by actively blocking the traffic.


### Host-based Sensors
- Hardware or software that monitors system activity.
- Monitors system logs, file integrity, and other system activity.
- Can be used to detect unauthorized access or changes to the system.
- They are usually software running on the hosts (eg servers, workstations, etc), they monitor the CPU, memory, and disk usage, and can also monitor the system logs, file integrity, and other system activity.

### Ways of collecting network data
- Ways to collect data on a network
  - Network Tap
  - Port Mirroring
- Network Tap
  - Hardware connected inline between two nodes in the network

Firewall <-> Network Tap <-> Router

The network tap collects all the data that passes between the firewall and the router, and sends it to the IDS for analysis.


### Collecting Data
- Port Mirroring
  - A feature on a network switch that allows the switch to send a copy of network packets to a network monitoring device.
  - The switch sends a copy of the network traffic to the IDS for analysis.

![img](https://i.imgur.com/509ZW0i.png)


### Network Sensors 
- Network Sensors should be placed at strategic points in the network to monitor inbound and outbound traffic to all devices on the network.
  - Internet gateway
    - So that it can monitor all traffic entering and leaving the network.
  - Connection between one LAN and another
    - So that it can monitor traffic between different parts of the network.
  - Remote Access Server that receives dial-up or VPN connections
    - So that it can monitor traffic from remote users.
  - Virtual Private Network (VPN) concentrator
    - So that it can monitor traffic from remote users.

Management programs control the sensors and collect data from them. The management programs can be used to configure the sensors, collect data from them, and analyze the data.

- Sensors can be also be positioned at either side of the firewall
  - Behind the firewall is a more secure location

![img](https://i.imgur.com/eRMZeo4.png)


### Sensor Deployment Concerns

- Sensor placement
  - Sensors should be placed at strategic points in the network to monitor inbound and outbound traffic to all devices on the network.

- Throughput
  - The amount of data that the sensor can process in a given amount of time.
  - The sensor should be able to handle the amount of traffic on the network.
  - Results in sensor dropping packets if it cannot keep up with the traffic.
  - On a high-traffic network, the sensor may not be able to capture all the packets.


- Security
  - The sensor should be secure from tampering.
  - It should be able to detect if someone tries to tamper with it.
  - Sensors cannot be a target for attackers.
  - Sensors may contain sensitive data and should be protected from unauthorized access.
  - Compromised sensors can be unreliable and may provide false data.


## Alerting System

An "Alerting System" in the context of Intrusion Detection Systems (IDS) and Intrusion Prevention Systems (IPS) is a component that notifies network administrators or security personnel when suspicious or malicious activity is detected. The alerts can be in the form of emails, SMS, dashboard notifications, or even automated responses that can help mitigate the detected threat. The alerting system is a crucial part of IDS and IPS as it enables timely response to potential security incidents.


- Trigger
  - Circumstances that cause the alerting system to generate an alert to be sent
  - The trigger can be a specific event or a combination of events

- Types of triggers
  - Detection of an anomaly
  - Detection of a known attack signature
  - Targeted monitoring of a specific system or network


## Anomaly Detection (Profile-based Detection)
- Anomaly detection is a method of detecting attacks by identifying deviations from normal behavior.
- It is based on the assumption that most network traffic is legitimate and that any deviation from the norm is likely to be an attack.

- Make use of profiles
  - For each autorized user or system, a profile is created that describes the normal behavior of that user or system.
    - This can detect potential insider threats
      - User suddenly downloading large amounts of data
      - User laptop is suddenly sending large amounts of data to an external IP address
- However human behaviour is not consistent, and can change over time
  - This can lead to false positives
    - Insurance agent A may access sensitive customer data at 2am as he has a presentation the next day
- Accuracy problems
  - False negatives
    - An attack that is not detected
  - False positives
    - A non-attack that is detected

# Some Definitions
- False Positive
  - An alert that is generated when no attack is actually occurring
- False Negative
  - An attack that is not detected by the IDS
- True Positive
  - An alert that is generated when an attack is actually occurring
- True Negative
  - No alert is generated when no attack is actually occurring

## Misuse or attack signature Detection (rule-based Detection)
- An attack signature is a sequence of events that is known to be associated with a particular attack.
 
- Misuse Detection triggers alarms based on signatures of known attacks
  - The IDS has a database of known attack signatures
  - When it detects a sequence of events that matches a known attack signature, it triggers an alarm
  - The database of attack signatures is updated regularly to include new attack signatures

- Can start protecting the network immediately
  - As soon as the attack signature is known, it can be added to the database
  - The IDS can then detect the attack




Here's a more detailed comparison between Anomaly Detection (also known as Behavior-based detection) and Misuse Detection (also known as Signature-based detection) in the context of Intrusion Detection Systems (IDS):


| Detection Method | Advantages | Disadvantages |
|------------------|------------|---------------|
| Anomaly Detection | - Can detect unknown threats (zero-day exploits)<br>- Adapts to changing network conditions<br>- Can identify insider threats<br>- Learns from the network behavior over time | - High false positive rate<br>- Requires a training period to establish a 'normal' baseline<br>- May raise alarms for legitimate activity that deviates from the norm<br>- Difficult to determine the exact cause of the anomaly |
| Misuse Detection | - High accuracy for known threats<br>- Low false positive rate<br>- Fast and efficient<br>- Easy to understand and manage | - Unable to detect unknown threats<br>- Needs regular updates of the signature database<br>- Can be evaded with slight modifications to attack patterns<br>- May not be effective against zero-day threats |

This table is not exhaustive and the advantages and disadvantages can vary based on the specific implementation and configuration of the IDS.


# Target Monitoring
- Target Monitoring is a method of detecting attacks by monitoring specific systems or networks that are likely to be targeted by attackers.

- Ususally implemented by calculating a checksum for target files/directories
  - If the checksum changes, it could indicate that the file has been tampered with

- Different Agents can be used to monitor different systems
  - For example, a file integrity agent can monitor the integrity of files on a server
  - A network agent can monitor network traffic
  - A database agent can monitor database activity

- Agents often need to coorperate with each other
  - For example, a file integrity agent may need to coorperate with a network agent to detect an attack
  

# Data Correlation

- IDS will collect data from multiple sources
  - Network sensors
  - Host-based sensors
  - Target monitoring agents

- One attack attempt can cause events to be recorded in multiple places
  - For example, a network sensor may detect an attack, and a host-based sensor may detect the same attack
- Data Correlation
  - Associating an event from one source with an event from another source
  - This can help to determine the scope of an attack

# Console
A console is a user interface that allows the system administrator to manage the IDS. The console provides a way to configure the IDS, view alerts, and manage the system.

- Provides a way to configure the IDS
  - For example, to add new attack signatures to the database

- Provide a way to view alerts
  - For example, to view alerts that have been generated by the alerting system

- IDS can collect information from multiple sensors
  - The console can be used to view information from all the sensors

- Command Console should run on a computer that is dedicated solely to the IDS
  - This is to prevent the IDS from being compromised
  - To maximize the security of the IDS, the console should be on a separate network from the rest of the network
  - Speed and reliability are important for the console

# Response System
- The response system takes action based on the alerts generated by the alerting system.
- IDS can be setup to take some countermeasures
  - For example, to block an IP address that is attacking the network
  - To block a port that is being attacked
  - To block a specific type of traffic that is being attacked

- Response system do not substitute for other security measures
  - For example, a firewall should still be used to block unwanted traffic
  - The response system should be used to complement other security measures

## Database of Attack Signatures or Behavior Profiles

- IDSs make use of information for comparing the traffic they monitor against known attack signatures or behavior profiles

## Signature-based Detection
- References a database of known attack signatures
- If a traffic matches a signature, an alert is generated
- Database of signatures is updated regularly

## Anomaly-based Detection
- Store normal profile information in a database
- If traffic deviates from the normal profile, an alert is generated

# Examining Intrusion Prevention System Components Step by Step

1. Installing IDS Database
2. Gathering Data
3. Sending alert messages
4. The IDS response system
5. The administrator accesses the damage through the console
6. Following escalation procedures
7. Logging and reporting the incident

![img](https://i.imgur.com/6dwuBDV.png)



## Step 1: Installing IDS Database
- The IDS database contains a list of known attack signatures
- The database is updated regularly

### Anomaly based detection
- May require a training period to establish a 'normal' baseline
- IDS observes the network traffic and learns from it

### Signature based detection
- IDS uses a database of known attack signatures
- When it detects a sequence of events that matches a known attack signature, it triggers an alarm
- The database of attack signatures is updated regularly to include new attack signatures

## Step 2: Gathering Data
- Sensors collect data from the network and systems
- The sensors send the data to the alerting system for analysis
- The sensor needs to be positioned where they can capture all data
- Sensor on individual hosts can monitor the CPU, memory, and disk usage, and can also monitor the system logs, file integrity, and other system activity

- If the network is too heavy, there is a chance that network sensors may not be able to capture all the packets
  - This is called "dropping packets"

## Step 3: Sending Alert Messages

- The alerting system generates alerts based on the data collected by the sensors
- IDS software compares the data it collects to the database of attack signatures
- If it detects a match, it generates an alert

## Step 4: The IDS Response System
- The response system takes action based on the alerts generated by the alerting system
- The response system can be configured to take action to stop the attack
- The console will receive the alerts and the administrator can take action
- IDS can be configured to take action when a suspeicious packet is received
  - For example, to block an IP address that is attacking the network
  - To block a port that is being attacked
  - To block a specific type of traffic that is being attacked

## Step 5: The Administrator Accesses the Damage Through the Console
- The console provides a user interface for the system administrator to manage the IDS
- The console can be used to view alerts that have been generated by the alerting system
- The administrator also needs to fine tune the IDS to reduce false positives
  - The goal is to avoid false positives and false negatives

## Step 6: Following Escalation Procedures

- The administrator follows escalation procedures
- The administrator may need to escalate the incident to a higher level of authority
- Should be spelled out in company policy
  - Incident levels
    - Level 1: Minor incident
    - Level 2: Major incident
    - Level 3: Catastrophic incident

## Step 7: Logging and Reporting the Incident
- The IDS logs the incident
- The administrator can generate a report on the incident
- The report can be used to analyze the incident and to improve the security of the network
- The report can be used to improve the security of the network
- Some system also have built-in reporting tools

# Types of IDS 
- Network-based IDS
- Host-based IDS
- Application-based IDS
- Wireless IDS
- Hybrid IDS

# Network-based intrusion detection system (NIDS)
- A network-based intrusion detection system (NIDS) is a system that monitors network traffic for suspicious activity and issues alerts when such activity is discovered. It is a passive system, meaning it does not take any action to prevent the attack. It is a monitoring system that is used to monitor the network traffic and system activity for any malicious activity or violation of the security policy.

- Common locations for NIDS sensors 
  - Beind a firewall before the LAN
  - Between the firewall and DMZ 
  - Any network segment

Management programs control the sensors and collect data from them. The management programs can be used to configure the sensors, collect data from them, and analyze the data.

- NDIS usually handles a high volume of traffic 
- May require dedicated hardware to handle the load


# Freeware NIDS: Snort
- Snort is a free and open source network intrusion prevention system (NIPS) and network intrusion detection system (NIDS) created by Martin Roesch in 1998. Snort is now developed by Cisco, which purchased Sourcefire in 2013. It is capable of performing real-time traffic analysis and packet logging on IP networks. It can perform protocol analysis, content searching/matching, and can be used to detect a variety of attacks and probes, such as buffer overflows, stealth port scans, CGI attacks, SMB probes, OS fingerprinting attempts, and much more.

- Ideal for small to medium-sized businesses
  - Because it doesn't comsume a lot of resources (CPU, memory, etc)
- Intended for installation on a computer that is dedicated solely to the IDS
- Comes with a collection of rules files
- Separate rules files for different types of attacks
  - For example, there are separate rules files for detecting attacks on web servers, email servers, and DNS servers
  - Port scans, DoS attacks, and other types of attacks

# Developing IDS filter rules
- IDS filter rules are used to detect attacks
- The rules are used to compare the data collected by the sensors to the database of attack signatures


# Rule Actions
- Can configure IDS to take action 
  - Other then simple triggering of alerts
  - For example, to block an IP address that is attacking the network
- This helps provide another layer of security
- Some IDSs include documentation on how to configure the IDS to take action
- Customized rules can increase the effectiveness of the IDS
  - Test your rules before deploying them into the production environment

## Snort
Snort rules
```bash
alert tcp any any -> any any
```
It means that the IDS will alert on any TCP traffic

```bash
alert tcp any any -> any 80
```
It means that the IDS will alert on any TCP traffic to port 80

```bash
alert tcp any any -> any 80 (msg:"HTTP traffic detected";)
```
It means that the IDS will alert on any TCP traffic to port 80 and the message "HTTP traffic detected" will be included in the alert


- Action on what snort will use
  - Alert: Generate an alert
  - Log: Log the packet
  - Pass: Ignore the packet
  - Activate: Enable a rule
  - Dynamic: Load a shared object
  - Drop: Drop the packet
  - Reject: Drop the packet and send a TCP reset
  - Sdrop: Drop the packet without logging it

- To make snort more precise, you can use the "content" keyword
  - For example, to detect the word "attack" in the packet
  - content:"attack";
- Can also use 
  - msg: to include a message in the alert
  - sid: to include a signature ID in the alert
  - ttl: to include a time-to-live value in the alert
  - id: to include an IP ID in the alert
  - flags: to include TCP flags in the alert
  - ack: to include an acknowledgment number in the alert
  - content: to include the content of the packet in the alert
  - logto: to include a log file in the alert


# Host-Based Intrusion Detection System (HIDS)
Deployed on individual hosts, such as servers and workstations, to monitor system activity and detect malicious activity. HIDS can monitor system logs, file integrity, and other system activity. It is a monitoring system that is used to monitor the system activity for any malicious activity or violation of the security policy.


- Deployed on a host in LAN
  - Host could be a server, router or a workstation
- Evaluate the security of the host
  - Monitor the CPU, memory, and disk usage
  - Monitor the system logs, file integrity, and other system activity

Gathers data such as 
- System logs
- File integrity
- CPU, memory, and disk usage
- File system changes
- User activity
- Log files
- Network Connections

## HIDS configuration
- Centralized Configuration
  - All the HIDS are configured from a central location
  - This makes it easier to manage the HIDS
  - The central location can be a server or a workstation

- Distributed configuration
  - Each HIDS is configured separately
  - This makes it more difficult to manage the HIDS
  - The HIDS can be configured from a central location

# Hybrid IDS Implementation

- Hybrid IDS is a combination of NIDS and HIDS
- Gains flexibility and coverage
- Can be more effective than using NIDS or HIDS alone

Combining IDS sensor locations
- Put sensors at strategic points in the network
  - For example, behind the firewall, between the firewall and DMZ, and on any network segment
- Can report attacks aimed at a particular host
  - For example, a host-based sensor can report an attack aimed at a particular host

# IDS Hardware Appliances
- Can handle more traffic than software-based IDS
  -  They can also have better stability and reliability
-  Plug and Play Capabilities
  -  Easy to install and configure
-  Upgrade appliances
  -  Can be upgraded with new hardware and software
-  Can be more expensive than software-based IDS

# HIDS
- Tripwire is a popular HIDS
- They can create a baseline snapshot of the system
  - This is a snapshot of the system when it is known to be secure
  - The HIDS can then compare the current state of the system to the baseline snapshot

Any future changes to the file will be deleted


# Developing a Security Incident Response Team (SIRT)
- A security incident response team (SIRT) is a group of people who are responsible for responding to security incidents. The team is responsible for identifying, analyzing, and responding to security incidents. The team is also responsible for developing and implementing security policies and procedures. The team is responsible for coordinating the response to security incidents with other teams within the organization, such as the IT team, the legal team, and the public relations team.

- Their responsibilities include
  - Identifying, analyzing, and responding to security incidents
  - Developing and implementing security policies and procedures
  - Coordinating the response to security incidents with other teams within the organization


- Goal of a SIRT
  - To minimize the impact of security incidents
  - To prevent security incidents from occurring
  - To develop and implement security policies and procedures
  - To coordinate the response to security incidents with other teams within the organization
  
- Primary functions of a SIRT
  - Preparation
    - Developing and implementing security policies and procedures
    - Developing and implementing security awareness training
  - Notification
    - Notifying the appropriate teams within the organization of a security incident
  - Response
    - Identifying, analyzing, and responding to security incidents
    - Coordinating the response to security incidents with other teams within the organization
  - Countermeasures
    - Developing and implementing countermeasures to prevent security incidents from occurring
  - Recovery
    - Recovering from security incidents
    - Developing and implementing security policies and procedures to prevent security incidents from occurring
  - Follow-up
    - Following up on security incidents to ensure that they have been resolved
    - Developing and implementing security policies and procedures to prevent security incidents from occurring


