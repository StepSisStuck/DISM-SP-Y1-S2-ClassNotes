# Topic 2b - Security Systems

# Table of Contents

- [Topic 2b - Security Systems](#topic-2b---security-systems)
- [Table of Contents](#table-of-contents)
- [Threat Intelligence](#threat-intelligence)
- [Categories of Threat Intelligence](#categories-of-threat-intelligence)
- [Confirm Boot Intergrity](#confirm-boot-intergrity)
- [Protecting Endpoints](#protecting-endpoints)
- [Monitoring and Response Systems](#monitoring-and-response-systems)
- [Hardern Endpoints](#hardern-endpoints)
  - [Operating Systems](#operating-systems)
- [Monitoring and Response Systems](#monitoring-and-response-systems-1)
- [Hardern Endpoints](#hardern-endpoints-1)
  - [Operating Systems](#operating-systems-1)

-------------------------

# Threat Intelligence
- Organizations are increasingly using threat intelligence to help them identify and prioritize potential threats.
- One type of shared infomation is evidence of attacks that have been detected and blocked by security controls.
- Key Risk Indicators (KRIs) are metrics that are used to measure the level of risk that an organization is exposed to.
   - These indicators are used to measure the effectiveness of security controls and to identify areas where improvements are needed.

- KRI are exceeding it normal range, it is an indication that the organization is at risk of a security breach but it is still operating within acceptable limits.
- IOC (Indicator of Compromise) is a piece of information that indicates that a security breach has occurred or is occurring.
   - IOCs are used to identify the presence of malware or an attacker on a network.
    - IOCs can be used to identify the presence of malware or an attacker on a network.

- Two categories of threat intelligence:
   - Open source intelligence (OSINT)
      - "Open source" means that the information is available to anyone.
      - OSINT is information that is collected from publicly available sources.

    - Closed source intelligence (CSINT)
       - CSINT is information that is collected from private sources.
       - All information that is collected by an organization is CSINT.
       - CSINT is also known as proprietary intelligence.


# Categories of Threat Intelligence
- Two concerns around public infomation sharing centers are that:
   - Privacy 
      - An organization might not want to share information about a security breach because it could damage its reputation.

    - Speed 
      - Automated Indicator Sharing (AIS) enable the exchange of cyberthreat indicators between organizations in real time.
- The two tools facilitate AIS
    - Structured Threat Information eXpression (STIX)
   - STIX is a language for describing cyberthreats.
   - STIX is a language for describing cyberthreats.
   - STIX is a language for describing cyberthreats.
   - STIX is a language

    - Trusted Automated Exchange of Intelligence Information (TAXII)
   - TAXII is a protocol for exchanging cyberthreat information.
   - TAXII is a protocol for exchanging cyberthreat information.
   - TAXII is a protocol for exchanging cyberthreat information.
   - TAXII is a protocol for exchanging
  
  ![img](https://i.imgur.com/MjOKJzZ.png)

  - Securing endpoint computers primarily involves three major tasks:
     - Installing and updating antivirus software
     - Installing and updating antimalware software
     - Installing and updating host-based firewalls

  # Confirm Boot Intergrity
  - Ensuring secure boot is enabled on Unified Extensible Firmware Interface (UEFI) systems.
  - Unified Extensible Firmware Interface (UEFI) is a replacement for BIOS.
      - Early booting process used firmware called BIOS (Basic Input/Output System).
      - To add support for new hardware, BIOS had to be updated.
      - UEFI Includes 
         - The ability to boot from large disks 2.2 TB or larger
         - Support for modern firmware standards such as Extensible Markup Language (XML) and Simple Network Management Protocol (SNMP)
         - Faster boot times
         - Support for network booting in IPv4 and IPv6 networks to aid in the deployment of operating systems

- Boot Security 
    - The abilty to ubdate the BIOs in firmware opened the door for a threat actor to create malware to infect the BIOS.
    - Boot Security is a feature of UEFI that prevents malware from infecting the BIOS.
    - The process begins with Validation of boot software, then it can validate the software drivers and OS kernel.
       - Chain of Trust because each component in the boot process is validated before the next component is loaded.
       - The strongest starting point is hardware, which cannot be modified by malware.

# Protecting Endpoints
- Protections on a computer endpoints can be accomplished by:
   - Installing and updating antivirus software
   - Installing and updating antimalware software
   - Installing and updating host-based firewalls

Antivirus Software
- Antivirus software is designed to detect and remove viruses from a computer.
- Antivirus software is designed to detect and remove viruses from a computer.
- Antivirus software is designed to detect and remove viruses from a computer.

- Anti-malware software is designed to detect and remove malware from a computer.
- Antimalware is a suite of software that includes antivirus software and other tools.
- Antimalware spam protection is often included in antimalware software.
    - Filters by analyzing every word in the message and comparing it to a list of words that are commonly used in spam messages.

- Another component of an antimalware suite is a antispyware, which helps protect against spyware.
- Uses pop-up blockers to prevent pop-up ads from appearing on a computer.

- Web Browsers 
   - Web browsers offers the following security on endpoint computer:
   - Secure Cookies are sent to a web server only when a request is made using a secure connection.
      - This prevents an unauthorized user from intercepting the cookie and using it to impersonate the user.

    - Pop-up blockers prevent pop-up ads from appearing on a computer.

    - Private browsing mode prevents the browser from storing information about the websites that the user visits.
       - This includes cookies, temporary internet files, and browsing history.

 Credits : [Itzkvth-Tan](https://github.com/Itzkvth-Tan)
# Monitoring and Response Systems
There are three types of monitoring and response systems for endpoint computers:
1)Host Intrusion Detection Systems (HIDS) is a software-based applications that runs on an endpoint computer and can detect if there is an attack occured.
 
2)Host Instrusion Prevention Systems (HIPS) monitor endpoint to immediately block malicious attack by following specific rules.
 
3)Endpoint Detection and Response (EDR) tools are considered more powerful than (HIDS and HIPS)
-An EDR can aggregate data from multiple endpoint computers to a centralized database
-EDR tools can perform more advance analytics that identify patterns and detect anomalies.
 
 
 
 
 
# Hardern Endpoints
*Hardening endpoints involves patch management and OS protections*
*Patch Management*
 
Effective patch management involves two types of patch management tools to administer patches
*Patch distribution using an automated patch update service.
*Patch reception in Windows 10 includes
- Forced Updates
- No Selective Updates
- More efficient distribution
 
 

## Operating Systems
 
Securing an OS involves proper security configuration and confinement tools
A typical OS security configuration should include
-Disabling unnecessary ports and services
-Disabling default accounts/passwords
-Employinng least functionality
Windows 10 Tamper protection security feature prevents Windows security settings from being changed or disabled by a threat actor who modifies the registry
-A Group Policy setting can prevent access to registry editing tools
 
Confinement Tools - tools used to restrict malware
-Application whitelisting/blacklisting
-Sandbox
-Quarantine



 
 Credits : [Itzkvth-Tan](https://github.com/Itzkvth-Tan)
# Monitoring and Response Systems
There are three types of monitoring and response systems for endpoint computers:
1)Host Intrusion Detection Systems (HIDS) is a software-based applications that runs on an endpoint computer and can detect if there is an attack occured.
 
2)Host Instrusion Prevention Systems (HIPS) monitor endpoint to immediately block malicious attack by following specific rules.
 
3)Endpoint Detection and Response (EDR) tools are considered more powerful than (HIDS and HIPS)
-An EDR can aggregate data from multiple endpoint computers to a centralized database
-EDR tools can perform more advance analytics that identify patterns and detect anomalies.
 
 
 
 
 
# Hardern Endpoints
*Hardening endpoints involves patch management and OS protections*
*Patch Management*
 
Effective patch management involves two types of patch management tools to administer patches
*Patch distribution using an automated patch update service.
*Patch reception in Windows 10 includes
- Forced Updates
- No Selective Updates
- More efficient distribution
 
 

## Operating Systems
 
Securing an OS involves proper security configuration and confinement tools
A typical OS security configuration should include
-Disabling unnecessary ports and services
-Disabling default accounts/passwords
-Employinng least functionality
Windows 10 Tamper protection security feature prevents Windows security settings from being changed or disabled by a threat actor who modifies the registry
-A Group Policy setting can prevent access to registry editing tools
 
Confinement Tools - tools used to restrict malware
-Application whitelisting/blacklisting
-Sandbox
-Quarantine

![img](https://i.imgur.com/X8aZbtS.png)

 