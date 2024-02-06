# Chapter 5, working with Windows and CLI systems

# Table of Contents

# Objectives 
- Explain the purpose of the Windows registry
- Discrbe the structure of the Microsoft File Structure
- Explain the structure of NTFS disk
- List some options for decrypting drives encrypted with Whole Disk Encryption
- Explain how Windows Registry
- Discribe Microsoft Startup Tasks
- Explain the purpose of a Virtual Machine

# Understanding the File System
- File system
  - Gives the OS a road map to data on the disk
- Type of file system an OS uses dertermines how data is stored on the disk
- When you need to access on a suspect computer to acquire evidence or inspect data
  - You should be familiar with the file system used by the OS
  
# Understanding the Boot Sequence

- Computer boot sequence
  - BIOS
  - MBR
  - Boot loader
  - Kernel
  - OS

- Complemetary Metal-Oxide Semiconductor (CMOS)
  - Stores the BIOS settings
  - Stores the date and time
  - Stores the boot sequence
  - Stores the boot order

- Basic Input/Output System (BIOS)
  - Firmware that initializes the hardware
  - Performs a power-on self-test (POST)
  - Loads the boot loader
- Master Boot Record (MBR)
  - The first sector of a hard drive
  - Contains the boot loader
  - Contains the partition table
- Bootstrap process 
    - Contained in ROM (Read-Only Memory), that tells the computer how to start up
    - Displays the keys or key you need to press to enter the BIOS setup
      - Loads the BIOS
          - Performs a power-on self-test (POST)
              - Loads the boot loader
                  - Loads the kernel
                    - Loads the OS


- CMOS should be modified to boot from a forensic floppy disk or CD-ROM 
   - This prevents evidence from being altered


## BIOS can configure the following:
- Boot sequence
- Date and time
- Passwords
- Power management
- Plug and play
- Hardware settings
- Security settings
- System event log
- Error handling
- Integrated peripherals
- USB configuration
- PCI configuration
- IDE configuration
- ACPI configuration
- PnP/PCI configuration
- PC Health status
- Load default settings
- Save and exit setup


# Understanding Disk Drives
- Disk Drives are made up of one or more platter coated with magnetic material
- Disk Drive components
  - Geometry (Cylinders, Heads, Sectors)
  - Head
  - Tracks
  - Cylinders 
  - Sectors
    - Typically 512 bytes


- Properties handles at the drive's hardware or firmware level includes:-
- Zone bit recording (ZBR)
  - Groupings track by zones ensures that all tracks have the same number of sectors
    - Explaination
    Zone Bit Recording (ZBR) is a method used in hard drives to optimize the storage capacity. 

(In a hard drive, data is stored in concentric circles called tracks. In traditional hard drives, each track would have the same number of sectors (the smallest unit that can be written to or read from). This means that outer tracks, which are longer, have the same number of sectors as inner tracks, which are shorter. This is not an efficient use of space because the outer tracks could hold more data if they had more sectors.

ZBR addresses this inefficiency by grouping tracks into zones based on their distance from the center of the disk. Each zone has a different number of sectors per track, with outer zones having more sectors than inner zones. This allows for more data to be stored on the disk. 

The line "Groupings track by zones ensures that all tracks have the same number of sectors" seems to be a bit misleading. In the context of ZBR, it's more accurate to say that within each zone, all tracks have the same number of sectors. But different zones will have a different number of sectors per track.)


- Track density
  - The number of tracks per inch, the smaller the space, the more track on platter

- Explantion
  - Track density is the number of tracks per inch on a hard drive platter. The higher the track density, the more data that can be stored on the platter. This is because there are more tracks available to store data.

