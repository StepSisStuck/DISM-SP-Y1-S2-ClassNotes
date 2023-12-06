# LAS01 Oracle Linux Boot Process and Common Linux Utilities

# Table of Contents



# How to do Root recovery in Linux

1. Reboot the system
2. Press e to edit the boot loader, make sure to press fast enough to interrupt the boot process
3. Once you have successfully 'interrupted' the boot process at the Grub menu. You will be able to see the following bootloader set parameters screen
4. You may scroll down to the line that starts with linux and add the following to the end of the line:
```bash
init=/sysroot/bin/sh
```
5. Press Ctrl+x to boot the system with the new parameter
6. You will be presented with a shell prompt
7. Remount the root filesystem with read and write permissions
```bash
mount -o remount,rw /
```
8. Change the root directory to the sysroot directory
```bash
chroot /sysroot
```
9. Change the root password
```bash
passwd root
```
10. Create a file named .autorelabel in the root directory
```bash
touch /.autorelabel
```
11. Exit the chroot environment
```bash
exit
```
12. Reboot the system
```bash
reboot
```
13. Once the system has rebooted, you will be able to login as root with the new password



# GRUB and Linux Boot Process
1. Ensure the server is powered on, the server will serve as a repository for your client

2. (On client) Login as root and start terminal 

3.  Type the following command
```bash
grub2-setpassword
```
This command will prompt you to enter a password for the grub bootloader

When prompted, enter the password `0rcle86`

4. Display the content of user.cfg file to show the generated hash
```bash
cd /boot/grub2
cat user.cfg
```
5. Recreate the GRUB2 configuration file
```bash
grub2-mkconfig -o /boot/grub2/grub.cfg
```

# Test ssh connnection between systems, and different ways to login
## First way
1. Ensure the server and client is powered on

2. (On client) Login as root and start terminal

3. Type the following command
```bash
ssh peter@<your server ip address>
```
FYI, make sure to type your username, if it is not peter, replace it with your username!!!

4. When prompted, enter the password of the username

5. You should be able to login to the server

6. That's it, you have successfully tested the ssh connection between the server and client!

## Check the current IP address of the client
1. Ensure the server and client is powered on
2. (On client) Login as root and start terminal
3. Type the following command
```bash
ifconfig
```
4. You should be able to see the IP address of the client

## Second way
1. Login to the server as student

2. Type the following command
```bash
ssh <your server ip address>
```
They should give you a long string of characters, and ask you if you want to continue connecting, type yes

3. When prompted, enter the password of the username, if not, they will only just prompt you to enter the password as your server has username is the same as your client 
   
4. You should be able to login to the server

5. That's it, you have successfully tested the ssh connection between the server and client! 
```bash
Exit
```
Close the connection

## By Defult the ssh connection is using port 22, now we will change it to another port
1. Login to the server as root

2. Type the following command
```bash
netstat -tulpn | grep sshd
```
3. You should be able to see the port 22 is being used by sshd

### Checking the port number from another device
1. Ensure the server and client is powered on
2. (On client) Login as root and start terminal
3. Type the following command
```bash
dnf repolist
```
4.  Install nmap
```bash
dnf install nmap -y
```
5. Type the following command
```bash
nmap <your server ip address>
```
After your installation, you should be able to type the command above

This will be able to show you the port number of the server, something like this
```bash
Starting Nmap 7.91 ( https://nmap.org ) at 2021-06-21 15:20 +08
Nmap scan report for <your server ip address>
Host is up (0.00016s latency).
Not shown: 997 closed ports
PORT     STATE SERVICE
22/tcp   open  ssh
111/tcp  open  rpcbind
631/tcp  open  ipp
3306/tcp open  mysql
```
6. That's it, you have successfully checked the port number of the server!

### Changing the port number
1. Login to the server as root
2. Type the following command
```bash
nano /etc/ssh/sshd_config
```
3. Go to the line that says `Port 22` and change it to `#Port 22`
4. Now below the line that says `#Port 22` add a new line that says `Port 8222`
5. Save the file and exit
6. The current (default) SELinux policy does not allow sshd to bind to a port other than 22. To allow sshd to bind to port 8222, you need to change the SELinux policy for sshd to allow it to bind to port 8222
```bash
semanage port -a -t ssh_port_t -p tcp 8222
```
7. Restart the sshd service
```bash
systemctl restart sshd
```
8. Type the following command
```bash
netstat -tulpn | grep sshd
```
9. You should be able to see the port 8222 is being used by sshd
10. That's it, you have successfully changed the port number of the server!
11. Since we are not listening to port 22 anymore, We should configure the firewall to block port 22
```bash
firewall-cmd --remove-service=ssh --permanent
firewall-cmd --reload
```

12. Lets check the port number from another device
13. Ensure the server and client is powered on
14. (On client) Login as root and start terminal
15. Type the following command
```bash
nmap <your server ip address>
```
16. You should be able to see the port number of the server, something like this
```bash
Starting Nmap 7.91 ( https://nmap.org ) at 2021-06-21 15:20 +08
Nmap scan report for <your server ip address>
Host is up (0.00016s latency).
Not shown: 997 closed ports
PORT     STATE SERVICE
111/tcp  open  rpcbind
631/tcp  open  ipp
3306/tcp open  mysql
```
17. That's it, you have successfully checked the port number of the server!
18. But if you want to SSH into the server, let's try
```bash
ssh -p 8222 <your server ip address>
```
19. You are not able to SSH into the server, because the firewall is blocking the port 8222

20. Let's configure the firewall to allow port 8222
```bash
firewall-cmd --add-port=8222/tcp --permanent
firewall-cmd --reload
```
21. Now you should be able to SSH into the server
```bash
ssh -p 8222 <your server ip address>
```
22. That's it, you have successfully SSH into the server!


## How to revert back to the default port 22
1. Login to the server as root
2. Type the following command
```bash
nano /etc/ssh/sshd_config
```
3. Go to the line that says `#Port 22` and change it to `Port 22`
4. Now below the line that says `Port 22` add a new line that says `#Port 8222`
5. Save the file and exit
6. Restart the sshd service
```bash
systemctl restart sshd
```
7. Type the following command
```bash
netstat -tulpn | grep sshd
```
8. You should be able to see the port 22 is being used by sshd
9. That's it, you have successfully changed the port number of the server!
10. Since we are not listening to port 8222 anymore, We should configure the firewall to block port 8222 and a
```bash
firewall-cmd --remove-port=8222/tcp --permanent
firewall-cmd --reload
```
```bash
firewall-cmd --add-service=ssh --permanent
firewall-cmd --reload
```

# Secure Copy (scp) and Secure File Transfer Protocol (sftp)

In this section, we have successfully downloaded the file from the server to the client using 3 different ways (scp, sftp, and ssh) which they are using the same port number 22

SSH - provides a secure channel over an unsecured network in a client-server architecture, connecting an SSH client application with an SSH server

SCP - is a secure copy protocol that is used to securely copy files between remote hosts

SFTP - is a secure file transfer protocol that is used to securely transfer files between remote hosts

1. Login in to the server as root

2. Type the following command
```bash
touch /tmp/practice
```
We create a file named practice in the /tmp directory

3. Now login to the client as root
4. Type the following command
```bash
scp <server IP address>:/tmp/practice .
```
The . at the end of the command is to copy the file to the current directory

Similarly to SSH, you will be prompted to enter the password of the username

5.  Check if the file is copied to the current directory
```bash
ls -l 
```
6. That's it, you have successfully copied the file from the server to the client!

## Using Secure File Transfer Protocol (sftp)
1. Login to client as root
2. Type the following command
```bash
sftp peter@<server IP address>
```
Make sure to type your username, if it is not peter, replace it with your username!!!

3. When prompted, enter the password of the username
4. You should be able to login to the server
5. At the sftp> prompt, type the following command
```bash
pwd
ls -a
```

6. Download the file .bash_profile from the server to the client
```bash
get .bash_profile peter_profile
```

7. Check if the file is downloaded to the current directory
```bash
ls -l p*
```
The p* is to show the file that starts with p


# Introduction to cockpit web console
What is cockpit web console?

Cockpit is a web console that makes it easy to administer your Linux servers via a web browser. You can perform tasks such as starting containers, administering storage, configuring networks, and inspecting logs.

1. Login to the server as root
2. Type the following command
```bash
dnf install cockpit -y
```
3. Type the following command
```bash
systemctl enable --now cockpit.socket
systemctl start cockpit
```
4. Type the following command
```bash
systemctl status cockpit
netstat -tulpn | grep 9090
```
5. You should be able to see the port 9090 is being used by cockpit
6. Configure the firewall to allow port 9090
```bash
firewall-cmd --add-port=9090/tcp --permanent
firewall-cmd --reload
```
7. Now you should be able to access the cockpit web console from another device, login as root in client
8. Go to firefox and enter your server IP address with port 9090
```bash
https://<your server IP address>:9090
```

# Network Configuration
1. Login on Client as root
2. Type the following command
```bash
man nmcli
```
The nmcli is a command-line tool for controlling NetworkManager and reporting network status. It can be utilized as a replacement for nm-applet or other graphical clients. It is not meant as a replacement for nm-connection-editor though, so you might still want to install that GNOME package.

3. Type the following command
```bash
nmcli device
```
The command is to show the network devices in the system.

4. To view more detailed information about a specific device, type the following command
```bash
nmcli d show <device>
```
Example:
```bash
nmcli d show ens160
```
The command is to show the current network configuration for the device ens160.

The output will be something like this
```bash
GENERAL.DEVICE:                         ens160
GENERAL.TYPE:                           ethernet
GENERAL.HWADDR:                         00:50:56:8B:5C:5C
GENERAL.MTU:                            1500
GENERAL.STATE:                          100 (connected)
GENERAL.CONNECTION:                     ens160
GENERAL.CON-PATH:                       /org/freedesktop/NetworkManager/ActiveConnection/1
WIRED-PROPERTIES.CARRIER:               on
IP4.ADDRESS[1]:                         192.168.1.131
IP4.GATEWAY:                            192.168.1.1
IP4.ROUTE[1]:                           dst = 
IP4.ROUTE[2]:                           dst =
IP4.DNS[1]:                             192.168.30.2
```

5. Another useful comand is 
```bash
ip addr show <device>
```
Example:
```bash
route -n
```
This command `route -n` is to show the routing table of the system

6. Under the Network Manager Service, the current DNS settings will be published to the /etc/resolv.conf file. Thus to view the current DNS settings, type the following command
```bash
cat /etc/resolv.conf
```
This will show you the current DNS settings, something like this
```bash
# Generated by NetworkManager
search <domain>
nameserver 192.168.10.131
```


# Kernal Parameters
Linux Kernal parameters can be used to change some core resources of the system. 

1. Login to the server as root
2. Type the following command
```bash
sysctl -a
```
This command is to show all the current kernal parameters of the system

3. Type the following command
```bash
sysctl -a | grep icmp
```
This command is to show all the current kernal parameters of the system that contains the word icmp

3. Type the following command
```bash
sysctl -w net.ipv4.icmp_echo_ignore_all=1
```
This command is to change the kernal parameter of the system


# Preventive Login
1. Login to the client as student
2. Type the following command
```bash
sudo -i
```
They will say that you are not in the sudoers file, this incident will be reported

3. Type the following command
```bash
su -
```

4. Edit the sudoers file
```bash
nano /etc/sudoers
```
5. Add the following line to the file
```bash
student ALL=(ALL) ALL
```
6. Save the file and exit
7. Now you should be able to login as student and use the sudo command
```bash
sudo -i
```
8. That's it, you have successfully added the student to the sudoers file!