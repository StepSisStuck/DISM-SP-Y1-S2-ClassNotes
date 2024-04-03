# Chapter 4 Digital Forensic Tools

# Table of Contents
- [Chapter 4 Digital Forensic Tools](#chapter-4-digital-forensic-tools)
- [Table of Contents](#table-of-contents)
- [Evaluating DigitaL Forensic Tools](#evaluating-digital-forensic-tools)
- [Types of Digital Forensic Tools](#types-of-digital-forensic-tools)
- [Task Performed by Digital Forensic Tools](#task-performed-by-digital-forensic-tools)
  - [Acquisition](#acquisition)
    - [Validation and Verification](#validation-and-verification)
    - [Extraction](#extraction)
    - [Reconstruction](#reconstruction)
    - [Reporting](#reporting)
    - [Acquisition subfunctions](#acquisition-subfunctions)
- [Considerations for tools](#considerations-for-tools)
  - [Considerations](#considerations)
- [GUI Forensic Tools](#gui-forensic-tools)
- [Digital Forensics Hardware Tools](#digital-forensics-hardware-tools)
- [Forensic Workstation](#forensic-workstation)
  - [Recommendations for a Forensic](#recommendations-for-a-forensic)
  - [Recommendations when choosing stationary or lightweight workstation:](#recommendations-when-choosing-stationary-or-lightweight-workstation)
- [Write blockers](#write-blockers)
- [Validating and Testing Forensic Software](#validating-and-testing-forensic-software)
- [Using National Institute of Standards and Technology Tools](#using-national-institute-of-standards-and-technology-tools)
  - [Your lab must meet the following criteria for tool testing](#your-lab-must-meet-the-following-criteria-for-tool-testing)
- [Using validation protocols](#using-validation-protocols)
- [Summary](#summary)

-----------------

# Evaluating DigitaL Forensic Tools
- Consider open-source tools; the best tools are often free as they are developed by the community and have many features

- Questions to ask when evaluating tools:
  - Is the tool easy to use?
  - On which platforms does the tool run? (Which OSs?) 
  - Can a script be written to automate the tool?
  - Does it have automated reporting features?
  - Does it have a GUI?
  - What is the vendor's reputation?
  - Does the tool have a good support community?

# Types of Digital Forensic Tools
- Hardware forensic tools
   - Range from single-purpose devices components to complete computer systems and servers
- Software forensic tools
   - Range from single-purpose tools to complete suites of tools
   - Range up from free to very expensive
   - Types
     - Command-line tools
     - GUI tools
    -   Commonly used to acquire data from a suspect system to an image file


# Task Performed by Digital Forensic Tools
- Follow guidelines set up by NIST's Computer Forensic Tool Testing (CFTT) program
- ISO standard 27037:2012 states : Digital Evidence First Responders (DEFRs) should use validated tools

- All computer forensic tools, both hardware and software, perform specific functions. These functions can be grouped into 5 major categories:
    - Acquisition
    - Validation and verification
    - Extraction
    - Reconstruction
    - Reporting

## Acquisition
- The process of creating an exact image of a suspect's storage device
- The image is a bit-by-bit copy of the original storage device
- The image is created in a forensically sound manner
- The image is verified to ensure that it is an exact copy of the original storage device


- Two types of data-copying methods are used in software tools:
  - Physical copying of the entire storage device
  - Logical copying of the data on the storage device which is only the data in the logical partitions

- The formats for disk acquistitions vary 
  - From raw data to vendor-specific formats


- Creating smaller segmented files is a typical feature in vendor acquistion tools
  - Creating smaller segmented files is a typical feature in vendor acquistion tools - segmented files are smaller and therefore can be copied to other media more easily
   
   - Remote acquisition of files is common in larger organizations
     - Popular remote acquisition tools include EnCase Enterprise, AccessData's FTK Enterprise, and Guidance Software's EnCase Enterprise
     - Remote acquisition tools are used to acquire data from a suspect system over a network

### Validation and Verification
- Validation
  - A way to confirm that a tool is functioning as intended and that the tool is not damaged or corrupted

- Verification
  - A way to confirm that the data acquired by the tool is an exact copy of the original data
  - The tool compares the hash value of the original data with the hash value of the acquired data
  - A related process is filtering, which is used to remove known files from the acquired data

- Subfunctions of validation and verification
  - Hashing
    - CRC32, MD5, SHA-1, SHA-256, SHA-512
    - This is to ensure that the data is not changed
  - Filtering
    -  To seprate known files from the acquired data
    -  Based on file extensions, file names, and file sizes
  - Encryption
    -  To encrypt the acquired data
    -  To protect the data from unauthorized access
    -  To protect the data from being changed
  - Analysis file header 
    - To analyze the header of the acquired data
    - To determine the type of the acquired data

- National Software Reference Library (NSRL) has a list of known files
  - The list is used to filter known files from the acquired data
  - The list is updated regularly
  - The list is available at http://www.nsrl.nist.gov/Downloads.htm

- Many computer forensic tools include a list of common header value
  - With this information, you can see whether a file extention is incorrect for the file type

### Extraction
- The process of extracting data from a storage device
- The data is extracted from the image file created during the acquisition process
- The data is extracted in a forensically sound manner
- The data is extracted in a manner that does not change the original image file

- Subfunctions of extration
  - File carving
    - To extract files from the acquired data
    - To extract files that are not in the file system
    - To extract files that are deleted
  - File viewer
    - To view the contents of the acquired data
    - To view the contents of the extracted files
  - File search
    - To search for files in the acquired data
    - To search for files in the extracted files
  - File decryption
    - To decrypt the acquired data
    - To decrypt the extracted files
  - File hashing
    - To hash the acquired data
    - To hash the extracted files
  - File analysis
    - To analyze the acquired data
    - To analyze the extracted files
  - File reporting
    - To create a report of the acquired data
    - To create a report of the extracted files

- Keyword search speed is an important feature in forensic tools
  - The speed of keyword search depends on the number of files in the acquired data
  - The speed of keyword search depends on the size of the acquired data

- From a investigation perspective, encrypted files and systems are a problem 
- Many password recovery tools have a featire for generating possible passwords lists
  - The lists are based on the user's personal information
  - The lists are based on the user's habits
  - The lists are based on the user's password history

- If a password dictionary attack fails, you can run a brute-force attack

### Reconstruction
- The process of reconstructing data from the acquired data
- Re-create a suspect drive to show how the suspect used the drive - Another reason is to create a copy of suspect data for use in court

- Methods of reconstructions 
  - Disk to Disk copy 
  - Partition to Partition copy
  - Image to Disk copy
  - Image to Partition copy
  - Rebuilding file from data runs and carving

- To recreate an image of a suspect drive
  - Copy an image to another location, such as partition or disk or a virtual machine
  - Simplest method is to use a tool that makes a direct disk to image copy

- Example of disk-to-image copy tools:
  - Linux dd command
  - ProDiscover
  - Voom Technologies Shadow Drive

### Reporting
- The process of creating a report of the acquired data
- The report is created in a forensically sound manner

- Subfunctions of reporting
  - File reporting
  - To create a report of the acquired data
  - To create a report of the extracted files
  
  

### Acquisition subfunctions
- Physical data copy
- Logical data copy - logical partitions
- Data acquisition format - raw data format
- GUI acquisition
- Remote, live (logon) and memory acquisition


-----------------

# Considerations for tools 
## Considerations
- Flexibility
- Reliability
- Future proofing

- Create a software library containing older versins of forensic utilities, Oss and other software

# GUI Forensic Tools
- GUI forensic tools are easier to use than command-line tools
- Have also simplified training for new forensic examiners
- Most of them are putting together as suits of  tools
- Advantages of GUI forensic tools
  - Easy to use
  - Easy to learn
  - Easy to train
  - Easy to automate
  - Easy to report
  - Easy to document
  - Easy to present in court

- Disadvantages of GUI forensic tools
   - Not as flexible as command-line tools
   - Not as customizable as command-line tools
   - Excessive resource requirements - PC RAM and CPU
   - Produce inconstant results - Because the type of OS used, 32-bit or 64-bit, and the type of file system used, FAT32 or NTFS, can affect the results
 - Create tool dependencies 
   - Create a single point of failure - If the tool fails, the entire investigation can be affected
   - Should be familiar with more then one tool

# Digital Forensics Hardware Tools

- Technology changes rapidly
- Hardware eventually fails
- Schedule equipment
replacements periodically
- When planning your budget consider:
    - Amount of time you expect the forensic workstation to be running
    - Failures –how often does it fail?
    - Consultant and vendor fees –support the h/w
     - Anticipate equipment replacement –the more you use, the more the equipment will breakdown

# Forensic Workstation
- A forensic workstation is a computer system that is used to perform forensic analysis
- Carefully consider whatto include in a forensic workstation
- Categories of forensic workstation 
  - Stationary forensic workstation
  - Portable forensic workstation
  - Lightweight forensic workstation

- balance what you need and what your system can handle 
- Consider the following when building a forensic workstation:
  - CPU
  - RAM
  - Storage
  - Video card
  - Network card
  - Monitor
  - Keyboard
  - Mouse
  - Power supply
  - Case
  - Cooling system
  - Operating system
  - Forensic software
  - Write-blocker
  - Cables
  - Adapters
  - Other peripherals

- Police agency labs 
  - Need many forensic workstations
  - User serveral PC configurations - due to diverse investigations

- Keep a hardware library in addition to your software library 

- Private corporation labs
  - Handle only systems types used in the organization

- Build a forensic workstation is not as difficult as it sounds
   - Advantages 
     - Customized to your needs
     - Save money

    - Disadvantages
      - Hard to find support for problems
      - Can be expensive if you make mistakes

- Also need to identify what you intend to analyze
  
 ## Recommendations for a Forensic
Workstation
- Some vendors offer workstations designed for
digital forensics
-  Having vendor support can save you time and
frustration when you have problems
- Can mix and match components to get the
capabilities you need for your forensic workstation
- Determine where data acquisitions will take place
- i.e acquire data in the field, may want to carry
something light

## Recommendations when choosing stationary or lightweight workstation:
- Full tower to allow for expansion devices
- As much memory and processor power as budget allows
- Different sizes of hard drives
- 400-watt or better power supply with battery backup
- External FireWire and USB 2.0 ports
- Assortment of drive adapter bridges
- Ergonomic keyboard and mouse
- A good video card with at least a 17-inch monitor
- High-end video card and dual monitors

If you have a limited budget, one option for
outfitting your lab is to use high-end game PCs –
can perform well with modifications!


# Write blockers
- Prevents data writes to a hard disk
  -  A write blocker is any tool that permits read-only access to data storage devices without compromising the integrity of the data

- Software - enabled blocking
  -  Typically run in a shell mode (Windows CLI)
  -  Example: PDBlock from Digital Intelligence

- Hardware options
  - Ideal for GUI-based tools
    -  They prevent Windows or Linux from Writing to the suspect drive

  - Ast as a bridge between the suspect drive and the forensic workstation
    -  They prevent the suspect drive from being mounted by the OS
    -  They prevent the suspect drive from being written to by the OS

- Hardware write blockers are more reliable than software write blockers

- You can navigate to the blocked drive with any application and view the contents of the drive - No problem accessing the drive

- Discards the written data
  -  For the OS the data copy is successful

- Connecting technology
  -  IDE
  -  SATA
  -  SCSI
  -  USB
  -  FireWire
  -  eSATA
  -  SAS

# Validating and Testing Forensic Software
- It is important to make sure the evidence you recover and analyze can be admitted in court
- You must test and validate the forensic software you use to prevent the software from being challenged in court

# Using National Institute of Standards and Technology Tools
-  NIST publishes articles, provides tools, and creates
procedures for testing/validating forensics software
- Computer Forensics Tool Testing (CFTT) project
  - Manages research on computer forensics tools
-  NIST has created criteria for testing computer
forensics tools based on:
   - Standard testing methods
   - ISO 17025 criteria for testing items that have no current standards


## Your lab must meet the following criteria for tool testing
 - Establish categories for digital forensics tools
 - Identify forensics category requirements
 - Develop test assertions :
   -   Based on the requirements, create tests to test tool’s capability
- Identify test cases
  - Establish a test method
  - Report test results

- ISO 5725 - specifies results must be repeatable
and reproducible

# Using validation protocols
- Always verify your results by performing the same tasks with other similar forensic tools
- Use at least two otools 
  - Retreiving and analyzing data
  - Verifying the results

- Understanding how forensic tools work
  -  Helps you understand how to use them
  -  Helps you understand how to validate them
  -  Helps you understand how to test them

- One way to compare results and verify a new tool is by using a disk editior, such as Hex Workshop or WinHex
  -  Compare the results of the new tool with the results of the disk editor

- Disk editors do not have a flashy interface but however they are:
  -  Are reliable
  -  Can access raw data

- Computer Forensics Examination Protocol 
  -   Perform the investigaton with a GUI tool
  -   Verify your results with a command-line tool
  -   Compare hash values of the acquired data

# Summary

The excerpt discusses the importance of using validation protocols to verify forensic tool results. It suggests using disk editors to compare results and verify new tools. The Computer Forensics Examination Protocol is also mentioned, which involves performing the investigation with a GUI tool, verifying results with a command-line tool, and comparing hash values of the acquired data.











