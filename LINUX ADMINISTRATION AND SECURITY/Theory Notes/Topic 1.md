# Topic 1

# Table of Contents

-----------------
# Root password recovery
- This is useful when you forget the root password
- This is done by booting the system into single user mode
- Impose a vulnerbility in the system

## How to do root password recovery
- Reboot the system
- Press e to edit the GRUB menu
- Find the line that starts with linux16
- Append rd.break to the end of the line
- Press Ctrl + x to boot into single user mode
- Remount the root partition in read/write mode
- Change the root password
- Reboot the system
- Login with the new password
- Change the SELinux context of the password file

```bash
# mount -o remount,rw /sysroot
# chroot /sysroot
# passwd
# touch /.autorelabel
# exit
# reboot
```

![img](https://i.imgur.com/baBCcJX.png)

## GRUB Menu Protect
- GRUB is the bootloader in linux
- It is used to boot the kernel
- To prevent the GRUB menu from being edited, we can set a password for it

```bash
# grub-md5-crypt
Password:   
Retype password:
```

- This will generate a hash

- Other protection methods
    - BIOS password
    - GRUB password
    - Single user mode password
    - Filesystem password
    - Kernel password
    - Boot loader password

# Overview of TCP/IP ports and port numbers range
- TCP/IP is a suite of protocols
- It is used to connect hosts on the internet
- Supports up to 65535 ports
- Port numbers are divided into 3 ranges
    - Well known ports (0-1023)
    - Registered ports (1024-49151)
    - Dynamic ports (49152-65535)

# Network configuration files
- Network configuration files are located in /etc/sysconfig/network-scripts
- The main configuration file is ifcfg-eth0
- ifcfg-eth0 is used to configure the first ethernet interface

# Network configuration
- The IP address can be used to show the IP address of the system

```bash
# ip addr show ens160
```

```bash
# ip route
```
- Any changes made by ip or ifconfig comands will be lost after reboot

- To permanently change the IP address, we need to edit the network configuration file

```bash
# nano /etc/sysconfig/network-scripts/ifcfg-ens160
```

- The configuration file will look like this
- The BOOTPROTO is set to dhcp by default
- We need to change it to static
- We also need to add the IP address, netmask and gateway
- We can also add the DNS server

## To bring a network interface up or down
- To bring a network interface up or down, we can use the ifup and ifdown commands

```bash
# nmcli c up ens160
# nmcli c down ens160
```

It is common that students bring down the network interface by clicking the Turn Off button in the GUI. This will not work in the exam. You must use the ifdown command.

# Kernel tuning
- Kernel tuning is used to improve the performance of the system
- Kernel parameters are stored in /proc/sys
- The sysctl command is used to view and modify kernel parameters

```bash
# sysctl -a
```

- To change a kernel parameter, we can use the sysctl command

```bash
# sysctl -w kernel.hostname=server1.example.com
```

# vsftpd.conf
- vsftpd.conf is the configuration file for vsftpd
- It is located in /etc/vsftpd
- The default configuration file is well documented

## ftpd_banner
- ftpd_banner is used to set the welcome message
- The default value is Welcome to blah FTP service
- We can change it to something else

## anonymous_enable
- anonymous_enable is used to enable or disable anonymous FTP
- The default value is YES
- We can change it to NO to disable anonymous FTP
- We can also change it to YES to enable anonymous FTP

## local_enable
- local_enable is used to enable or disable local FTP

# ftp chroot
- chroot is used to change the root directory of a process
- This is used to restrict the user to a specific directory
- Without chroot, the user can access the entire filesystem
- This is a security risk
- To enable chroot, we need to add the following line to vsftpd.conf

```bash
chroot_local_user=YES
```


This command will activate chroot for local users. We can also activate chroot for anonymous users by adding the following line to vsftpd.conf:

```bash 
choot_list_enable=YES
```

# SELinux
- SELinux is a security mechanism in Linux
- It is used to implement mandatory access control
- It is used to restrict the user's access to files and directories
- SELinux is enabled by default in CentOS 7
- SELinux is disabled by default in CentOS 6
- SELinux is disabled by default in RHEL 7
- Allows administrators to define highly detailed policies
- SELinux policies are stored in /etc/selinux

## SELinux state
- SELinux can be in one of the following states
    - Enforcing: Any violation will be blocked
    - Permissive: Any violation will be logged but not blocked
    - Disabled: SELinux is disabled

- To check the SELinux state, we can use the getenforce command
- To change the SELinux state, we can use the setenforce command

```bash
# getenforce
# setenforce 0
```






