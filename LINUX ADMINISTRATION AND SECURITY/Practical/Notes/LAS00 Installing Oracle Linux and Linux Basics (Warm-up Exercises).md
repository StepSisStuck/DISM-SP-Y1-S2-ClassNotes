# Commands in Linux Oracle for Lesson 0

# Table of Contents
- [Commands in Linux Oracle for Lesson 0](#commands-in-linux-oracle-for-lesson-0)
- [Table of Contents](#table-of-contents)
  - [nmcli device](#nmcli-device)
  - [nmcli d show ens160](#nmcli-d-show-ens160)
  - [nmtui](#nmtui)
- [shutdown now -r](#shutdown-now--r)
  - [hostnamectl](#hostnamectl)
  - [hostnamectl set-hostname ](#hostnamectl-set-hostname-)
  - [hostnamectl set-hostname .](#hostnamectl-set-hostname--1)
  - [ping  -c ](#ping---c-)
  - [systemctl disable libvirtd](#systemctl-disable-libvirtd)
  - [su - root](#su---root)
  - [ps -t pts/1](#ps--t-pts1)
  - [useradd ](#useradd-)
  - [passwd ](#passwd-)
  - [userdel ](#userdel-)
  - [groupadd ](#groupadd-)
  - [groupdel ](#groupdel-)
  - [usermod -aG  ](#usermod--ag--)
  - [groups ](#groups-)
- [nano text editor](#nano-text-editor)
  - [nano ](#nano-)
  - [cd](#cd)
  - [grep session /etc/practice](#grep-session-etcpractice)
  - [ls -l /etc/practice](#ls--l-etcpractice)
  - [chgrp  /etc/practice](#chgrp--etcpractice)
  - [chown  /etc/practice](#chown--etcpractice)
  - [chmod 777 /etc/practice](#chmod-777-etcpractice)
- [chmod](#chmod)
  - [chmod u=rw /tmp/practice](#chmod-urw-tmppractice)
  - [chmod g=r /tmp/practice](#chmod-gr-tmppractice)
  - [chmod o= /tmp/practice](#chmod-o-tmppractice)
  - [find /etc -name practice](#find-etc--name-practice)
  - [rpm -i ](#rpm--i-)
  - [telnet ](#telnet-)
  - [dnf clean all](#dnf-clean-all)
  - [dnf repolist](#dnf-repolist)
  - [systemctl status ](#systemctl-status-)



-----------------
## nmcli device
The command is to show the network devices in the system.
```bash
nmcli device
```
-----------------
## nmcli d show ens160

The command is to show the current network configuration for the device ens160.
```bash
nmcli d show <device>
```
-----------------
## nmtui 

The command is to show the network manager text user interface.
```bash
nmtui
```
-----------------
# shutdown now -r

The command is to shutdown the system now and reboot the system.
```bash
shutdown now -r
```
-----------------
## hostnamectl

The command is to show the hostname of the system.
```bash
hostnamectl
```

-----------------

## hostnamectl set-hostname <hostname>

The command is to set the hostname of the system.
```bash
hostnamectl set-hostname <hostname>
```

-----------------

## hostnamectl set-hostname <hostname>.<domain>

The command is to set the hostname and domain of the system.
```bash
hostnamectl set-hostname <hostname>.<domain>
```

-----------------

## ping <ip address> -c <count>

The command is to ping the ip address for a certain amount of time.
```bash
ping <ip address> -c <count>
```

-----------------

## systemctl disable libvirtd

The command is to disable the libvirtd service.
```bash
systemctl disable libvirtd
```

-----------------

## su - root

The command is to switch to root user.
```bash
su - root
```

-----------------

## ps -t pts/1

The command is to show the process of the pts/1.
```bash
ps -t pts/1
```

-----------------

## useradd <username>

The command is to add a user.
```bash
useradd <username>
```

-----------------

## passwd <username>

The command is to set the password for the user.
```bash
passwd <username>
```

-----------------

## userdel <username>

The command is to delete the user.
```bash
userdel <username>
```

-----------------
## groupadd <groupname>

The command is to add a group.
```bash
groupadd <groupname>
```

-----------------

## groupdel <groupname>

The command is to delete a group.
```bash
groupdel <groupname>
```

-----------------

## usermod -aG <groupname> <username>

The command is to add a user to a group.
```bash
usermod -aG <groupname> <username>
```

-----------------

## groups <usernames>

The command is to show the groups of the user.
```bash
groups <usernames>
```

example:
```bash
groups peter paul mary
```

-----------------

# nano text editor

The command is to open the nano text editor.
```bash
nano
```

-----------------

## nano <filename>

The command is to open the nano text editor with the file.
```bash
nano <filename>
```

-----------------
## cd 

The command is to change directory.
```bash
cd <directory>
```

-----------------

cat <filename>

The command is to show the content of the file.
```bash
cat <filename>
```

-----------------

## grep session /etc/practice

The command is to show the lines that contain the word session in the file.
```bash
grep session /etc/practice
```

-----------------

## ls -l /etc/practice

The command is to show the file details of the file.
```bash
ls -l /etc/practice
```

-----------------

## chgrp <groupname> /etc/practice

The command is to change the group of the file.
```bash
chgrp <groupname> /etc/practice
```

-----------------

## chown <username> /etc/practice

The command is to change the owner of the file.
```bash
chown <username> /etc/practice
```

-----------------

## chmod 777 /etc/practice

The command is to change the permission of the file.
```bash
chmod 777 /etc/practice
```

What is the number 777?

The number 777 is the permission of the file. The first 7 is the permission of the owner. The second 7 is the permission of the group. The third 7 is the permission of the others.

-----------------

# chmod

## chmod u=rw /tmp/practice

The command is to change the permission of the file. The u=rw is to change the permission of the user to read and write.
```bash
chmod u=rw /tmp/practice
```

## chmod g=r /tmp/practice

The command is to change the permission of the file. The g=r is to change the permission of the group to read.
```bash
chmod g=r /tmp/practice
```

## chmod o= /tmp/practice

The command is to change the permission of the file. The o= is to change the permission of the others to none.
```bash
chmod o= /tmp/practice
```
The targeted users will be referred using the combination of [ugoa]
ie. each letter represents one type of user: [u]ser, [g]roup,[o]ther, [a]ll
The effective file permissions will be the combination of [+-=] and [rwxXst]

-----------------

## find /etc -name practice

The command is to find the file in the directory.
```bash
find /etc -name <filename>
```

-----------------

## rpm -i <filename>

The command is to install the rpm file.
```bash
rpm -i <filename>
```

-----------------

## telnet <ip address>

The command is to telnet to the ip address.
```bash
telnet <ip address>
```

-----------------

## dnf clean all

The command is to clean the dnf cache.
```bash
dnf clean all
```

-----------------

## dnf repolist

The command is to show the repository list.
```bash
dnf repolist
```

-----------------

## systemctl status <system>

The command is to show the status of the system.
```bash
systemctl status <system>
```

-----------------


