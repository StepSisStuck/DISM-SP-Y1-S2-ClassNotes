# Chapter 5, working with Windows and CLI systems

# Table of Contents
- [Chapter 5, working with Windows and CLI systems](#chapter-5-working-with-windows-and-cli-systems)
- [Table of Contents](#table-of-contents)
- [Objectives](#objectives)
- [Understanding the File System](#understanding-the-file-system)
- [Understanding the Boot Sequence](#understanding-the-boot-sequence)
  - [BIOS can configure the following:](#bios-can-configure-the-following)
- [Understanding Disk Drives](#understanding-disk-drives)
- [Solid-State Drives](#solid-state-drives)
- [Exploring Microsoft File Structure](#exploring-microsoft-file-structure)
- [Disk Partitions](#disk-partitions)

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

- Areal Density
  - Number of Bits in one square inch of the disk

  - Explantion
    - Areal density is the number of bits that can be stored in a given area of a hard drive platter. It is typically measured in bits per square inch. The higher the areal density, the more data that can be stored on the platter. This is because there are more bits available to store data.


- Head and Cylinder skew
  - Head skew
    - The time it takes for the head to move from one track to another
  - Cylinder skew
    - The time it takes for the head to move from one cylinder to another


# Solid-State Drives
- All flash memory devices have a feature called wear leveling
  - Wear leveling
    - Ensures that the flash memory is used evenly
    - Prevents the flash memory from wearing out
    - Explantion
      - Wear leveling is a technique used in flash memory devices to ensure that the memory is used evenly. This helps to prevent the memory from wearing out prematurely. Wear leveling works by distributing write and erase cycles evenly across the memory. This helps to extend the life of the memory and improve its reliability.
- When dealing with Solid-State Devices, making a full forensic as soon as possible is crucial
  - In case you need to recover data from unallocated space
    - wear leveling can make it difficult to recover data from unallocated space


# Exploring Microsoft File Structure

- In Microsoft's file systems, data is stored in units called sectors, which are grouped into larger units called clusters. 
- A cluster can contain one or more sectors. Grouping sectors into clusters reduces the overhead of reading or writing files to a disk.

- Clusters are numbered sequentially, starting at 0 in NTFS and 2 in FAT file systems.
- The first sector of all disks is reserved for system information, including the boot record and a database of the file structure.
- The operating system assigns these cluster numbers, which are known as logical addresses. These addresses point to a relative position on the disk.
- The actual sector numbers are called physical addresses, which range from 0 to the last sector on the disk.
- The concept of clusters and their addresses is specific to a logical disk drive, which is a partition of the physical disk.


# Disk Partitions

- A partition is a logical drive that is created from free space on a physical disk. Each partition is formatted with a file system, such as FAT or NTFS, and is assigned a drive letter (C:, D:, and so on).
- Windows OSs can have three primary partitions followed by an extended partition that can contain multiple logical drives.

- Partition gap
  - The space between partitions
  - The space is not used by the file system
  - It is used to store the partition table and boot record
  - **This can use to hide data**

![img](https://i.imgur.com/dXKEVOU.png)


