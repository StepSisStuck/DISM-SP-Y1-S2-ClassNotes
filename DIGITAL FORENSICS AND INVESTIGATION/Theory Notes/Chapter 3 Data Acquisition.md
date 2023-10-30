# Chapter 3 Data Acquisition

## Table of Contents
- [Chapter 3 Data Acquisition](#chapter-3-data-acquisition)
  - [Table of Contents](#table-of-contents)
- [Data Acquisition Recap](#data-acquisition-recap)
- [Understanding Storage Formats for Digital Evidence](#understanding-storage-formats-for-digital-evidence)
  - [Raw Format](#raw-format)
  - [Proprietary Format](#proprietary-format)
  - [Advanced Forensic Format (AFF)](#advanced-forensic-format-aff)
- [Determining the Best Acquisition Method](#determining-the-best-acquisition-method)
  - [Creating a Disk-to-Image File](#creating-a-disk-to-image-file)
  - [Creating a Disk-to-Disk](#creating-a-disk-to-disk)
  - [Logical Acquisition or Sparse Acquisition](#logical-acquisition-or-sparse-acquisition)
  - [When making a copy, consider the following:](#when-making-a-copy-consider-the-following)
- [Contingency Planning for Image Acquisition](#contingency-planning-for-image-acquisition)
- [Using Acquisition Tools](#using-acquisition-tools)
- [Capturing an Image with ProDiscover Basic](#capturing-an-image-with-prodiscover-basic)
- [Capturing an Image with AccessData FTK Imager Lite](#capturing-an-image-with-accessdata-ftk-imager-lite)
- [Validating an Data Acquisition](#validating-an-data-acquisition)
- [Windows Validation Tools](#windows-validation-tools)
- [Using Remote Network Acquisition Tools](#using-remote-network-acquisition-tools)
- [Remote Acquistion Tool](#remote-acquistion-tool)
  - [Other functions of Remote Acquisition Tools](#other-functions-of-remote-acquisition-tools)
- [Other commercial acquisition tools include:](#other-commercial-acquisition-tools-include)
- [Magnet Axion](#magnet-axion)
- [PassMark Software ImageUSB](#passmark-software-imageusb)
- [Runtime Software](#runtime-software)
- [SourceForge](#sourceforge)
- [Carved File](#carved-file)
- [Parsed File](#parsed-file)
- [Summary](#summary)


----------------------
# Data Acquisition Recap

- Before we can analyze data, we need to acquire/secure it
- The goal of a forensic data acquisition is to create a forensic image of the data that is suitable for analysis and used in the court of law

# Understanding Storage Formats for Digital Evidence
- Data in a forensic acquisition is stored in a forensic image as an image file

- Basically, the image file can be in one of the three formats:
    - Raw format - Raw format is a bit-by-bit copy of the source drive
    - Advanced Forensic Format (AFF) - AFF is an open and extensible format that stores data in the form of metadata
    - Proprietary format - Proprietary formats are created by vendors and are not open to the public
  
## Raw Format
- Makes it possible to create a bit-by-bit copy of the source drive (Sequential flat file) 
    - In the past we only do bit-by-bit copy of the source drive to copy the data the same size as the source drive

- Advantages of Raw Format
    - Raw format is the most common format used for forensic acquisition
    - It is supported by most forensic tools
    - It is easy to create and verify
    - It is easy to convert to other formats
    - It is easy to mount and access
    - Fast to create and verify

- Disadvantages of Raw Format
     - Requires a destination drive that is the same size as the source drive
     - It is not possible to store multiple images in a single file
     - It is not possible to store metadata in the image file
     - It is not possible to compress the image file

## Proprietary Format
- Proprietary formats are created by vendors and are not open to the public

- Features of Proprietary Format
    - It is possible to store multiple images in a single file
    - It is possible to store metadata in the image file
    - It is possible to compress the image file - Saves disk space
    - Can split the image file into multiple files - Useful for storing the image on multiple DVDs and Provide Integrity Check
    - Can encrypt the image file - Useful for storing the image on a cloud storage
    - Can store the image file on a remote server - Useful for storing the image on a cloud storage

- Disadvantages of Proprietary Format
     - It is not possible to convert the image file to other formats
     - It is not possible to mount the image file
     - It is not possible to access the image file without the proprietary tool
     - Inability to access the image file without the proprietary tool can be a problem if the tool is no longer available
     - File size limitation for each segment of the image file - Typically 650 MB, can be adjusted up or down at a limit of 2 GB

- The Expert Witness Format is unofficial proprietary format created by Guidance Software for EnCase (ex - .E01)

## Advanced Forensic Format (AFF)
- Designed by Simson Garfinkel as an open and extensible format that stores data in the form of metadata

- Design goals 
  1. Provide compressed and uncompressed images - Saves disk space
  2. No restriction on the size of the image file - Can store images of any size
  3. Provide a way to store multiple images in a single file - Useful for storing the image on multiple DVDs
  4. Simple design with Extensibility - Easy to implement
  5. Open source for multiple platforms and Oss - Supported by multiple tools
  6. Vendors will have no implementation restrictions - No licensing fees or royalties
  7. Internal consistency checks - Provide Integrity Check

- File extentiins include .afd for segmented image and files and .afm for AFF metadata files
- AFF is **Open Source** and can be used by anyone

# Determining the Best Acquisition Method
- Types of acquisition
   - Static acquisition - Static acquisition is performed on a system that is not running
   - Live acquisition - Live acquisition is performed on a system that is running

- Four Methods of data collection
   - Disk-to-image file - Disk-to-image file is the most common method of data collection
   - Disk-to-disk - Disk-to-disk is used when the source drive is damaged
   - Disk-to-removable media - Disk-to-removable media is used when the source drive is damaged
   - Disk-to-network - Disk-to-network is used when the source drive is damaged
   - logical acquisition - Logical acquisition is used when the source drive is damaged
   - spare drive acquisition - Spare drive acquisition is used when the source drive is damaged

- Determining the best method of data collection
   - The best method of data collection depends on the type of data to be collected and the condition of the source drive
   - The best method of data collection is the one that is the least intrusive and the least destructive

## Creating a Disk-to-Image File
- Disk-to-image file is the most common method of data collection
- Can make more then one copy of the image file
- Copies are bit for bit identical
- ProDiscover, FTK Imager, SMART, Sleuth Kit, X-Ways Forensicsm, ILookIX, and EnCase are some of the tools that can be used to create a disk-to-image file

## Creating a Disk-to-Disk
- When the source drive is damaged, it is not possible to create a disk-to-image file
- Tools can be adjusted disk's geometry (cylinder, head, and sector) to match the geometry of the source drive
- Encase, SnapCopy, and SafeBack are some of the tools that can be used to create a disk-to-disk

## Logical Acquisition or Sparse Acquisition
(Collect evidence from a large drive can take a long time) - Reason using these methods are
- Use when your time is limited
    - Logical acquisition is used when the source drive is damaged OR capture only the files that are relevant to the case (Example: Only need to investigate the files in the Documents folder and ignore the rest of the files)
    - Sparse acquisition is collects fragments of unallocated space (deleted) data from a drive
- For large drives, it is possible to collect only the files that are relevant to the case
- For PST or OST files, it is possible to collect only the emails that are relevant to the case

## When making a copy, consider the following:
- Size of the source drive
    - Lossless compression might be useful (does not permeantly change the data) Targe does not need to be so big
    - Use digital signature to verify the integrity of the image file

- When woeking with large drives, an alternative is using **tape backup system** to create a backup of the source drive
    - Tape backup system is a good alternative for large drives
    - Tape backup system is not a good alternative for small drives
    - Tape backup system is not a good alternative for drives that are damaged

- Whether you can retain the disk: 
  - Sometimes after copy, the orginal disck may need to return to the owner

# Contingency Planning for Image Acquisition
- Create a duplicate copy of the image file and store it in a safe place
    - Incase of corruption, you can use the duplicate copy to create another image file

- Make at least two copies of the image file
    - One copy is used for analysis
    - The other copy is used for backup
    - Use different tools to create the two copies or techniques

- Copy **host protected area** (HPA - An area not visabale for OS on drive) of the disk as well
    - The purpose of HPA (Host Protected Area) is to provide a space on a hard drive that is not visible to the operating system. Vendors use this area to store diagnostic tools and recovery tools. In the context of the excerpt you provided, copying the HPA of the disk as well as the image file can be useful for contingency planning in case of corruption or other issues.
    - Consider using hardware acquisition tools that can access the drive at BIOS level so as to access HPA

- Be prepared to deal with bad sectors
    - Bad sectors are areas on a hard drive that are damaged and cannot be read or written to
    - Bad sectors are marked as bad sectors in the file system
    - Bad sectors are not copied during a disk-to-image file
    - Bad sectors are copied during a disk-to-disk
    - Bad sectors are copied during a disk-to-removable media
    - Bad sectors are copied during a disk-to-network
    - Bad sectors are not copied during a logical acquisition
    - Bad sectors are not copied during a spare drive acquisition

- Encrypted Drives
    - Whole disk might be encrypted with PGP/BitLocker/TrueCryp/etc.
    - May require user to provide decryption key - suspect may not cooperate or may not know the key

# Using Acquisition Tools
- Acquisition tools for Windows
- Advantages
    - Making acquiring evidence form a suspect's computer easy
        - Many tools are developed for Windows Platform
        - Especially when used with hot-swappable drive bays (i.e USB, Firewire, SATA, etc.)

- Disadvantages
   - Must protect acquired data with a well-tested write-blocker hardware device
   - Tools can't acquire data from disk's host protected area (HPA)
   - Some countries haven't accepted the use of a write-blocker as a standard practice (Need to check with local laws)

# Capturing an Image with ProDiscover Basic
- ProDiscover Basic is a free tool that can be used to create a disk-to-image file
- ProDiscover Basic is a Windows-based tool
- ProDiscover Basic can be used to create a disk-to-image file of a Windows, Linux, or Mac OS X system

- Connecting the suspect's drive to your computer
    - Use a write-blocker to connect the suspect's drive to your computer
    - Use a hot-swappable drive bay to connect the suspect's drive to your computer
    - Document the chain of evidence for the suspect's drive
    - Remove the suspect's drive from the computer and connect it to your computer
    - Create a storage folder on target drive to store the image file

- Using ProDiscover's Proprietary Acquisition Format
    - Select the source drive
    - Select the destination drive
    - Select the acquisition method
    - Select the acquisition options
    - Click the Start button to start the acquisition process
    - Click the Stop button to stop the acquisition process
    - Click the Verify button to verify the image file
    - Click the Close button to close the acquisition window

![img](https://i.imgur.com/4dHqjNl.png)

# Capturing an Image with AccessData FTK Imager Lite

Another free tool that can be used to create a disk-to-image file is AccessData FTK Imager Lite

- FTK Imager is windows data acquisition tool that includes with AccessData Forensic Toolkit (FTK)
- Designed for viewing evidence files and drives and Disk-to-Image file creation
- Makes disk-to-image file copies of evidence drives
    - At Logical Partition Level and Physical Drive Level
    - Can segment the image file

- Evidence Drive must have hardware write-blocker
   - Or run from a CD/DVD or USB drive such as MiniPE or Helix

![img](https://i.imgur.com/a3JXl4T.png)
    

- FTK Imager can't acquire a drive's host protected area (HPA)
- Using a Write-Blocking Device and follow these steps 
    - Boot the computer with a write-blocking device
    - Connect evidence drive to the computer
    - Connect target disk to write-blocking device
    - Start FTK Imager Lite
    - Create Disk Image - Use Physical Drive option

# Validating an Data Acquisition
- After creating an image file, you need to validate it
- Validation is the process of verifying that the image file is identical to the source drive
- Validation is performed by calculating a hash value for the image file and comparing it to the hash value of the source drive
- If the hash values are identical, the image file is identical to the source drive

- Vallidation Techniques
    - Hashing
    - Checksum
    - Parity
    - Cyclical Redundancy Check (CRC)
    - CRC-32
    - MD5
    - SHA-1 to SHA-512

# Windows Validation Tools
- Windows has no built-in tools for validating an image file
   - Third-party tools are available: Hexadecimal Editor such as WinHex, X-Ways Forensics, and EnCase

- Commercial Computers forensic programs have built-in validation features
   - Each tool uses a different method to validate an image file
   - Some tools use hashing, some use checksum, and some use CRC
   - ProDiscover's. .eve file contains metadata that can be used to validate an image file

- Raw format images does not contain metadata
   - Can't be validated using ProDiscover's. .eve file
   - Can be validated using hashing, checksum, or CRC

# Using Remote Network Acquisition Tools
- You can remotely connect to a suspect's computer and create a disk-to-image file
- Remote Acquisition Tools
    - ProDiscover
    - EnCase
    - FTK
    - X-Ways Forensics
    - SMART
    - ILookIX
    - Sleuth Kit

- Disadvantages 
  - Can't acquire data from disk's host protected area (HPA)
  - Anti-virus software may interfere with the acquisition process
  - Anti-spyware software may interfere with the acquisition process
  - Firewall software may interfere with the acquisition process
  - Network bandwidth may be limited
  - Suspect could easily install their own security software that trigger an alert when a remote connection is made

# Remote Acquistion Tool 
- Bring  able to connect to a suspect's computer remotely and create a disk-to-image file is useful when the suspect's computer is located in a different city or country

Here are the steps to connect to a suspect's computer remotely and create a disk-to-image file:
1. Install the remote acquisition tool on the suspect's computer
2. Perform a live acquisition
3. Encrypt the connection between your computer and the suspect's computer
4. Copy the suspect's RAM while the suspect's computer is running
5. Using optional stealth mode to hide the remote connection from the suspect while the suspect's computer is running

## Other functions of Remote Acquisition Tools
1. Capture a live image of the suspect's computer
2. Capture a live image of the suspect's computer's RAM
3. Capture a live image of the suspect's computer's swap file
4. Remotely view and listen to IP ports on a suspect's computer
5. Run hash comparisons on a suspect's computer
6. Create a hash inventory of all files on system remotely (a negative hash list) to establish a baseline of known files

# Other commercial acquisition tools include:
    - ProDiscover
    - EnCase
    - FTK
    - X-Ways Forensics
    - SMART
    - ILookIX
    - Sleuth Kit
    - Magnet Forensics
    - PassMark OSForensics
    - Paraben P2 Commander
  

  # Magnet Axion

- Magnet AXIOM is a digital forensics tool that is used to acquire and analyze digital evidence
- MA is able to recover digital evidence from computers, smartphones, and tablets including smartphones, cloud services, computer, and IoT devices

- MA is able to acquire data from the following sources:
    - Computer
    - Smartphone
    - Cloud
    - IoT

The exam tool help to find most relevant evidence and provide a report


- This tool is gaining popularity in the industry
  

# PassMark Software ImageUSB
- ImageUSB is a free tool that can be used to create a disk-to-removable media
- ImageUSB download link: https://www.passmark.com/products/imageusb/
- ImageUSB is a free utility that can be used to create a disk-to-removable media
- ImageUSB is a Windows-based tool
- ImageUSB can be used to create a disk-to-removable media of a Windows, Linux, or Mac OS X system

# Runtime Software
Runtime Software offers shareware
programs for data acquisition and
recovery:
- DiskExplorer for FAT and NTFS
- Features:
    - Create a raw format image file
    - Segment the raw format or compressed image
for archiving purposes
    - Access network computers’ drives


# SourceForge
 SourceForge provides several applications for
security, analysis, and investigations
- Was preferred source code repository and distribution
platform for free and open source software (FOSS) projects
- For a list of current tools, see:
    - http://sourceforge.net/directory/securityutilities/storage/archiving/os:windows/freshness:recentlyupdated


# Carved File
- A Carved file is a file that is stored in a non-contiguous manner on a hard drive
- Fine Carved involves searching for the next available space on a hard drive and storing the file in that space
- Carved files are often recovered from unallocated space where the file system information has been lost

To sum up, file carving techniques can be used to recover deleted files that are still present in unallocated space on a hard drive. When a file is deleted, its file system information is removed, but the actual data may still be present in unallocated space until it is overwritten by new data. File carving tools can search for and extract these deleted files from unallocated space, even if they are fragmented and stored in a non-contiguous manner.

# Parsed File

- A Parsed file is a file that is stored in a contiguous manner on a hard drive
- Parsed files are often recovered from allocated space where the file system information is still present

Parsed File is a file that is stored in a contiguous manner on a hard drive and is often recovered from allocated space where the file system information is still present.

# Summary
This document is about data acquisition in digital forensics. It covers the different storage formats for digital evidence, including raw format, proprietary format, and advanced forensic format (AFF). It also discusses the different methods of data collection, such as disk-to-image file, disk-to-disk, disk-to-removable media, disk-to-network, logical acquisition, and spare drive acquisition. The document also covers contingency planning for image acquisition, using acquisition tools, validating data acquisition, and using remote network acquisition tools. It also mentions some commercial acquisition tools, such as ProDiscover, EnCase, FTK, X-Ways Forensics, SMART, ILookIX, Sleuth Kit, Magnet Forensics, PassMark OSForensics, Paraben P2 Commander, and Magnet Axion. Finally, it provides information on some free tools, such as ImageUSB and Runtime Software, and a list of security, analysis, and investigation tools available on SourceForge.