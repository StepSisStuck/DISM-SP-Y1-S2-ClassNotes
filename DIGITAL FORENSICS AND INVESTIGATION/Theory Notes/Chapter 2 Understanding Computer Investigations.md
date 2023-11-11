# Chapter 2 Understanding Computer Investigations

# Table of Contents
- [Chapter 2 Understanding Computer Investigations](#chapter-2-understanding-computer-investigations)
- [Table of Contents](#table-of-contents)
  - [.2](#2)
- [Objectives](#objectives)
- [Taking a Systematic Approach](#taking-a-systematic-approach)
- [Assessing the case](#assessing-the-case)
- [Planning the investigation](#planning-the-investigation)
- [Securing your evidence](#securing-your-evidence)
- [Procudures for Private-Sector High-Tech Investigations](#procudures-for-private-sector-high-tech-investigations)
  - [Example 1: Employee Termination Cases](#example-1-employee-termination-cases)
  - [Example 2: Internet Abuse Investigations](#example-2-internet-abuse-investigations)
  - [Example : Email Abuse Investigations](#example--email-abuse-investigations)
  - [Example :  Industrial Espionage Investigations\\](#example---industrial-espionage-investigations)
- [Interviews and Interrogations in High-Tech Investigations](#interviews-and-interrogations-in-high-tech-investigations)
- [Understanding Data Recovery Workstations and Software](#understanding-data-recovery-workstations-and-software)
- [Setting Up your Workstation for Digital Forensics](#setting-up-your-workstation-for-digital-forensics)
  - [Additional Useful Tools](#additional-useful-tools)
- [Conducting the Investigation](#conducting-the-investigation)
- [Understanding Bit-Stream Copies](#understanding-bit-stream-copies)
- [Acquiring an Image of the Evidence Media](#acquiring-an-image-of-the-evidence-media)
- [Completing the case](#completing-the-case)
- [Critiquing the Case](#critiquing-the-case)
- [Summary](#summary)
----------

# Objectives
-  Describe how to prepare a digital forensics
investigation by taking a systematic approach
- Describe procedures for private-sector digital
investigations
-  Explain requirements for data recovery
workstations and software
- Summarize how to conduct an investigation,
including critiquing a case

![img](https://i.imgur.com/OxEE0q5.png)

# Taking a Systematic Approach
- Steps for problem solving
1. Make an initial assessment about the type of case you are working on 
     - Interview people
     - Decide what places to search
     - Decide what to search for
     - Decide what tools to use

2. Determin a preliminary **design or approach** to the case 
   - When to visit the crime scene

3. Create a detailed plan for the investigation 
   - What to do first, second, and so on
   - What tools to use
   - Checklists helps you to stay on track

4. Acquire the necessary tools and equipment
5. Obtain and copy the evidence
6. Identify the risks 
- Example
    - unable to access the evidence due to password change

7. Mitigate the risks to ensure original evidence is not damaged
8. Test the design like comparing the hash value of the original evidence and the copy

9. Conduct the investigation, Analyze the evidence and recover the digital evidence
10. Investigate the evidence that you have recovered
11. Create a report of your findings
12. Critique the case Self-evaluation to improve your skills

# Assessing the case
- Syetematically **outline** the case details include:-
 1. Situation
   - e.g. A company suspects that an employee is using company resources to run a side business, employee abuse case
   - e.g. A company suspects that an employee is stealing company secrets, employee theft case

2. Nature of the case
   - e.g. Employee abuse case
   - e.g. Employee theft case
   - e.g use email for personal use

3. Type of case
4. Type of evidence 
    - e.g. Email, documents, images, videos, audio files, hard drives, USB drives, CDs, DVDs, and other storage media

5. Known disk formats
    - e.g. FAT, FAT32, NTFS, HFS, HFS+, and EXT2
    - e.g. Windows, Mac OS, Linux, and UNIX
    - e.g. RAID 0, RAID 1, RAID 5, and RAID 10
6. Location of the evidence
    - e.g. On a computer, on a network, or on a mobile device

- Based on the information you have gathered, you can determine the type of case you are working on and the type of evidence you need to collect

# Planning the investigation
- A basic **Investigation Plan** should include the following information:-
 1. Acquire the evidence
  2. Completed an evidence from and establish a chain of custody (helps show where the files came from and who had access to them)
 3. Transport the evidence to a secure location
 4. Store the evidence in a **approved** secure container
 5. Prepare forensic workstations
 6. Retrieve the evidence from the secure container
    - To ensure infomation is confidential. Containers should be a locked fireproof safe or a locked cabinet in a locked room (A place where only authorized personnel can access)
    - The container should be made of a material that does not generate static electricity

7. Make a forensic copy of the evidence
    - The forensic copy should be an exact duplicate of the original evidence
    - The forensic copy should be stored in a secure location
    - The forensic copy should be verified by comparing the hash value of the original evidence and the forensic copy
    - The forensic copy should be analyzed instead of the original evidence

8. Return the evidence to the secure container
9. Process the copy of the evidence with the appropriate tools (EnCase, FTK, and ProDiscover)

- An evidence custody form helps you document what has been done with the original evidence and its forensic copy
    - Also called a chain of custody form

- Two types
  - Single evidence custody form
            - List each piece of evidence on a separate form
- Multiple evidence custody form

![img](https://i.imgur.com/1afeuat.png)

![img](https://i.imgur.com/Y5laDig.png)
  
# Securing your evidence
- Use **evidence bags** to secure and catalog the evidence
- Use computer safe products when collecting evidence
  - Anti-static bags
  - Anti-static gloves
  - Anti-static wrist straps
  - Anti-static mats
  - Anti-static pads

- Use well padded containers to transport evidence

- Use evidence tape to seal all openings
    - CD drive bays
    - Insertion slots for power supply cables and network cables
    - USB ports
    - FireWire ports
    - Serial ports
    - Parallel ports
    - Floppy drive bays
    - Expansion slots

- Write your initials and the date on the evidence tape to prove that you sealed the openings and the evidence has not been tampered with
- Consider computer specific evidence bags, temperature and humidity ranges, and tamper-evident seals
    - Make sure you have a safe environment to store the evidence and storing it until a secure evidence container is available

# Procudures for Private-Sector High-Tech Investigations
- As an investigator, you must be able to identify the type of case you are working on and the type of evidence you need to collect
- To cover all issues important to high-tech investigations, you should follow a systematic approach
- Ensure that the correct procedures are followed and that the evidence is handled properly
- Different types of cases require different procedures

## Example 1: Employee Termination Cases
- The majority of investigations in the private sector are employee termination cases as they are involved in abuse of corporate resources
- Incidents that create a hostile work environment are the predominat types of cases investigated
    - Viewing Pornographic material in a work environment
    - Sending offensive emails
    - Sending threatening emails
    - Accessing confidential information
    - Stealing company secrets
    - Accessing company resources for personal use
    - Using company resources to run a side business

- Organizations must have appropriate policies and procedures in place to deal with these types of incidents - consult with the organization's legal department/Human Resources department

## Example 2: Internet Abuse Investigations
- To conduct an investigation, you must have a clear understanding of the organization's policies and procedures
- You may also collect 
    - Organizational's Internet Proxy Server logs
    - Suspect's computer IP address
    - Suspect's computer MAC address
    - Suspect's Disk Drive
    - Your prefered computer forensic tool

- Recommended steps
    - Use standard forensic analysis tools to analyze the evidence
    - Use appropriate tools to analyze the Internet Proxy Server logs
    - Contact the network firewall administrator and request the firewall logs
    - Compare the data recoered from forensic analysis with the data from the Internet Proxy Server logs and the firewall logs
    - Continue analyzing the computer's disck drive data 

## Example : Email Abuse Investigations
- To conduct an investigation, you need 
  - An electronic copy of the email that contains message header data
  - If available, e-mail server logs records
  - For e-mail systems that store users' messages on a central server, you need to obtain a copy of the e-mail server logs
  - Access to the computer so you can perform a forensic analysis on it
  - Your preferred computer forensic tool

- Recommended steps
    - Use standard forensic analysis tools to analyze the evidence
    - Use appropriate tools to analyze the e-mail server logs
    - Compare the data recovered from forensic analysis with the data from the e-mail server logs
    - Continue analyzing the computer's disk drive data
    - For web-based email investigations, you need to obtain a copy of the web server logs. Use tools such as FTK's Internet Keyword Search to search for keywords in the web server logs
    - Examine the web browser's cache and history files

## Example :  Industrial Espionage Investigations\

- All suspected cases of industrial espionage should be reported to the appropriate law enforcement agency : **Very Common**
- Staff needed include: 
   - Computing investigator who is responsible for disk  forensics examinations
  - Technology specialist who is knowledgeable of the
suspected compromised technical data
  - Network specialist who can perform log analysis
and set up network sniffers
  - Threat assessment specialist (typically an attorney)


- Guidelines when initating an investigation
  1. Determine wheather this investigation involves a possible industrial espionage incident
  2. Consult with Corporate Attorney and Upper Management
  3. Dertermine what information is needed to substaintiate the claim
  4. Generate a list of keywords for disk forensics and sniffer monitoring
  5. List and collect rescorces needed for the investigation
  6. Determine the best time to initiate the investigation
  7. Initiate the investigation after obtaining approval from the appropriate management

- Planning considerations
  1. Examine all email of the suspected employee
  2. Search Internet newsgroups or message boards
  3. Initiate physical surveillance
  4. Examine facility access logs for sensitive areas
  5. Determine suspect location and travel plans in relation to vulnerable assets
  6. Study the suspect's work habits
  7. Collect all incoming and outgoing phone records
   

- Steps to conducting an industrial espionage case
1. Gather all personnel assigned to the investigation and brief then on the plan
2. Gather resources to conduct the investigation
3. Place surveillance systems at key locations
4. Discreeetly monitor and gather additional information
5. Collect all logs and other evidence
6. Report the findings to the appropriate management
7. Review the findings with the appropriate management

# Interviews and Interrogations in High-Tech Investigations
- Become a skilled interviewer and interrogator can take many years of practice

Definitions
- Interview 
  - Usually conducted to collect information from a witness or a suspect 
    - About specific facts related to an investigation

- Interrogation
    - Process of trying to get a suspect to confess to a crime

- Role as a computing investigator
    - Interview witnesses and suspects
    - Gather information
    - Determine the facts of the case
    - Determine the type of case
    - Determine the type of evidence
    - Determine the location of the evidence
    - Determine the type of tools needed to collect the evidence
    - Determine the type of tools needed to analyze the evidence
    - Determine the type of tools needed to recover the evidence
    - Determine the type of tools needed to present the evidence
    - Determine the type of tools needed to report the findings

- Ingredients of a successful interview
    - Preparation
    - Rapport
    - Questioning
    - Listening
    - Recording

# Understanding Data Recovery Workstations and Software
- Investigatuons are conducted on a data recovery workstation
    - In data recovery workstation, the customer or your company can recover data from a damaged hard drive

- Computer forensic workstation
        - A specially configured computer system that is used to examine and analyze digital evidence
        - Loaded with additional software and hardware tools that are not found on a data recovery workstation

- To avoid damaging the evidence, use:
    - Write-blockers
      - Enable you to boot into a suspect's computer without writing any data to the suspect's hard drive
      - Prevents the computer from writing data to the suspect's hard drive

# Setting Up your Workstation for Digital Forensics
- Basic Requirments
1. A workstation running Windows XP or later
2. A Write Blocker : Prevents the computer from writing data to the suspect's hard drive
3. Digital forensic acquisition tool
4. Digital forensic analysis tool
5. Target drive to receive the source or suspect disck data
6. Spare PATA( Parallel Advanced Technology Attachment) or SATA (Serial Advanced Technology Attachment) cables
7. USB Ports 

![img](https://i.imgur.com/J8a3iGS.png)

## Additional Useful Tools
- Network Interface Card (NIC)
- Extra USB ports
- FireWire ports
- SCSI ports
- Disk Editor Tools
- Text Editor Tools
- Graphics Viewer Tools
- Other Specialized Viewing Tools

  # Conducting the Investigation
  - Gather resources identified in investigation plan
  - Items needed 
        1. Original Storage Media
        2. Evidence Custody Form
        3. Evidence container for storage media
        4. Bit-stream copy of the original storage media
        5. Forensic workstation to copy and examine your evidence
        6. Securable evidence container in locker, cabinet or safe
   
# Understanding Bit-Stream Copies
- Bit-stream copy
    - An exact duplicate of the original storage media
    - Also called a mirror image or a forensic image
    - Bit-stream copy is used for analysis and investigation
    - The original storage media is used as evidence in court
    - The bit-stream copy is used to prove that the original storage media has not been tampered with
    - The bit-stream copy is used to prove that the original storage media has not been altered

- Bit-stream image  
  -  File comtaining the bit-stream of all data on a disk or partition
  -  Also knows as **image file** or **image**
  
![img](https://i.imgur.com/n4ObpiB.png)

# Acquiring an Image of the Evidence Media

- First Rule of Computer Forensics
    - Never work on the original evidence
    - Always work on a bit-stream copy of the original evidence

- Conduct your analysis only on a copy of the data that you have verified to be an exact duplicate of the original evidence
- Serveral vendor provide MS-DOS, Linux and Windows Acquisition tools
- The most common tools are
    - EnCase
    - FTK
    - ProDiscover
    - SafeBack

Windows require a write-blocker when acquiring data from FAT or NTFS partitions

# Completing the case
- You need to produce a **Final Report** that summarizes the case
- The report should include the following information
    - Case number
    - Case name
    - Case description
    - Case type
    - Case status
    - Case investigator
    - Case start date
    - Case end date
    - Case summary
    - Case findings
    - Case recommendations
    - Case conclusion
    - Case critique

- Repeatable Findings
    -  Repeatable findings are findings that can be duplicated by another investigator using the same tools and techniques
    -  Repeatable findings are important because they can be used to prove that the evidence has not been tampered with

- If required, use a report template to ensure that you include all the required information in your report
- Report should show conculusive evidence that the suspect is guilty

- Keep a written journal of your investigation
    - Your notes should include the following information
        - Date and time
        - Location
        - People involved
        - Evidence collected
        - Tools used
        - Findings
        - Recommendations
        - Conclusion
        - Critique

- Answer the six Ws:
    - Who
    - What
    - When
    - Where
    - Why
    - How
- You must also explain computer and network processes in simple terms

# Critiquing the Case
Ask yourself the following questions
1. How could you improve your performance in the
case?
2. Did you expect the results you found? Did the case
develop in ways you did not expect?
3. Was the documentation as thorough as it could
have been?
4. What feedback has been received from the
requesting source? 
5. Did you discover any new problems? If so, what are
they?
6.  Did you use new techniques during the case or
during research?

# Summary

 This excerpt is from Chapter 2 of "Understanding Computer Investigations" and provides guidance on how to critique a case in the context of computer investigations. The section suggests asking questions related to performance, expectations, documentation, feedback, new problems, and new techniques. The six Ws - who, what, when, where, why, and how - are also emphasized as important factors to consider when critiquing a case. Additionally, the section highlights the importance of explaining computer and network processes in simple terms. By asking these questions and considering these factors, investigators can improve their performance and documentation, and discover new problems and techniques. The section concludes with a summary.
