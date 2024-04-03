# Table of Content 
- [Table of Content](#table-of-content)
- [Samba Server Configuration](#samba-server-configuration)
- [Domain Name System (DNS) Server Configuration](#domain-name-system-dns-server-configuration)
- [System Monitoring and Performance Tools](#system-monitoring-and-performance-tools)
- [User Authentication \& Pluggable Authentication Modules (PAM)](#user-authentication--pluggable-authentication-modules-pam)


# Samba Server Configuration

1. **Samba Server and Client Installation:**
   - Install Samba server: `dnf -y install samba samba-client`
   - Install Samba client only: `dnf -y install samba-client`

2. **Starting and Enabling Samba Service:**
   - Start Samba service: `systemctl start smb`
   - Enable Samba service to start on boot: `systemctl enable smb`
   - Verify Samba service status: `systemctl is-enabled smb` and `systemctl is-active smb`

3. **Configuring Samba Shares:**
   - Create and configure a shared directory.
   - Edit `/etc/samba/smb.conf` to define shares, users, and permissions.
   - Use `smbpasswd -a username` to add Samba users.

4. **Firewall Configuration for Samba:**
   - Use `firewall-cmd` to allow Samba services through the firewall.

5. **SELinux Configuration for Samba:**
   - Configure SELinux settings for sharing directories securely.

6. **Mounting Samba Shares Automatically at Boot:**
   - Use `mount -t cifs` and update `/etc/fstab` for automatic mounting.

7. **Access Control:**
   - Configure anonymous and authenticated access to Samba shares.
   - Adjust permissions and ownership for shared directories.

8. **Encrypting SMB Traffic:**
   - Update smb.conf to enforce SMB traffic encryption.



9. **Install Samba Server and Client:**
   - `dnf -y install samba samba-client` for server installation.
   - `dnf -y install samba-client` for client-only installation.

10. **Service Management:**
   - Start service: `systemctl start smb`
   - Enable at boot: `systemctl enable smb`
   - Check status: `systemctl is-enabled smb; systemctl is-active smb`

11. **Configuration and Share Setup:**
   - Configure shares in `/etc/samba/smb.conf`.
   - Add users: `smbpasswd -a username`

12. **Firewall Configuration:**
   - Adjust firewall rules as needed for Samba.

13. **SELinux for Samba:**
   - Configure SELinux policies for sharing.

14. **Mounting Shares:**
   - Use `mount -t cifs` and edit `/etc/fstab` for automatic mounts.

15. **Access Control:**
   - Configure `/etc/samba/smb.conf` for anonymous or authenticated access.

16. **Encrypting SMB Traffic:**
   - Update `smb.conf` for SMB traffic encryption.



# Domain Name System (DNS) Server Configuration

Based on the DNS configuration document, here are the essential commands and steps you need to know for your practical test:

1. **Install DNS Server Packages:**
   - `dnf -y install bind bind-utils`

2. **Check Configuration File Ownership:**
   - `ls -l /etc/named.conf`

3. **Set Hostname:**
   - `hostnamectl set-hostname server.las.org`

4. **Edit DNS Configuration:**
   - Modify `/etc/named.conf` to configure DNS server settings, like `allow-query`, `forwarders`, and disabling `dnssec-validation`.

5. **Enable and Start DNS Services:**
   - `systemctl enable --now named`

6. **Test DNS Configuration:**
   - Use `dig` command to query DNS records, e.g., `dig sp.edu.sg`.

7. **Prevent `/etc/resolv.conf` Overwrites:**
   - Modify `/etc/NetworkManager/NetworkManager.conf` and restart the NetworkManager.

8. **Setup Forward and Reverse Lookup Zones:**
   - Edit zone declarations in `/etc/named.conf` and create respective zone files in `/var/named`.

9. **Zone Transfer Commands:**
   - For initiating zone transfers: `dig -t axfr las.org` and `host -l las.org`.

10. **Restrict Zone Transfers:**
   - Update `/etc/named.conf` to allow transfers from specific hosts.

11. **Reload or Restart DNS Service After Changes:**
   - `systemctl reload named` or `systemctl restart named`.

12. **Reset and Restore System DNS Settings:**
   - Adjust `/etc/NetworkManager/NetworkManager.conf` and `/etc/resolv.conf` to default settings.

13. **Disable DNS Service (if needed):**
   - `systemctl disable --now named`.

Let's break down the commands related to DNS configurations:

1. **`dnf -y install bind bind-utils`**: Installs the BIND DNS server and its utilities. `dnf` is the package manager for Fedora and related distributions, `-y` automatically answers yes to all prompts, `bind` is the DNS software package, and `bind-utils` includes utilities for testing and troubleshooting DNS.

2. **`ls -l /etc/named.conf`**: Lists the details of the `/etc/named.conf` file, which is the main configuration file for the BIND DNS server. This command shows file permissions, ownership, and file size.

3. **`hostnamectl set-hostname server.las.org`**: Sets the system's hostname to `server.las.org`. `hostnamectl` is used to change the hostname on systemd-based systems.

4. **Modifying `/etc/named.conf`**: This step involves editing the BIND DNS server's main configuration file to define how the DNS server behaves, including which clients can query the server (`allow-query`), where the server forwards queries it cannot resolve locally (`forwarders`), and whether or not to enforce DNSSEC validation (`dnssec-validation no`).

5. **`systemctl enable --now named`**: Enables the BIND DNS service (`named`) to start at boot and starts it immediately. `systemctl` is the control interface for systemd, `enable` sets the service to start at boot, and `--now` also starts the service immediately.

6. **Using `dig` to test DNS**: The `dig` command is used for querying DNS servers. It can be used to test the DNS server's response to ensure it is correctly resolving domain names.

7. **Modifying `/etc/NetworkManager/NetworkManager.conf` and restarting NetworkManager**: This step prevents the `/etc/resolv.conf` file from being overwritten by NetworkManager, allowing manual control over DNS settings.

8. **Setting up forward and reverse lookup zones**: Involves editing `/etc/named.conf` to declare zones and creating zone files under `/var/named`. This sets up domain name to IP mappings (forward lookup) and IP to domain name mappings (reverse lookup).

9. **Zone transfer commands (`dig -t axfr` and `host -l`)**: These commands are used to initiate zone transfers, which replicate DNS databases between servers. This is useful for backup or load balancing.

10. **Restricting zone transfers**: Updating `/etc/named.conf` to restrict which servers can request zone transfers, enhancing security by preventing unauthorized access to your DNS data.

11. **`systemctl reload named` or `systemctl restart named`**: Reloads or restarts the BIND DNS service to apply configuration changes. `reload` applies changes without dropping connections, while `restart` stops and starts the service anew.

12. **Resetting system DNS settings**: Adjusts NetworkManager and `resolv.conf` settings back to their defaults, useful for undoing custom DNS configurations.

13. **`systemctl disable --now named`**: Disables the BIND DNS service, preventing it from starting at boot, and stops it immediately if it's running.

# System Monitoring and Performance Tools

From the document on system monitoring, here are the essential commands and concepts:

1. **Monitoring Open Ports and Listening Services:**
   - `netstat -tunalp4` and `ss -tunalp4`: Display open ports and listening services, specifying TCP/UDP, numerical addresses, all connections, listening ports, process ID/names, and IPv4.

2. **Network Scanning:**
   - `nmap -Pn <serverIP>`: Scan for open ports and services on a server, assuming the host is online.

3. **Packet Capturing:**
   - `tcpdump icmp -i ens160`: Capture ICMP packets on the specified interface, useful for analyzing network traffic.

4. **Generating Log Messages:**
   - `logger -p authpriv.warning "Message"`: Create a custom log entry, useful for testing log configurations.

5. **Restarting Logging Service:**
   - `systemctl restart rsyslog`: Apply changes to the logging service configuration.

6. **Resolving IP Addresses in Logs:**
   - `logresolve < /var/log/httpd/access_log > output_file`: Resolve IPs to hostnames in web server logs.

7. **Real-time Log Monitoring:**
   - `swatch -c /etc/swatch/config -t /var/log/secure`: Monitor security logs for specific patterns, alerting as configured.

8. **General System Monitoring:**
   - Use tools like `df`, `du`, `top`, `ps`, `iostat`, `free`, `vmstat`, `sar` for disk usage, process activity, and system performance monitoring.


9. **`netstat -tunalp4` and `ss -tunalp4`**: These commands are used for monitoring network connections, including TCP and UDP ports that are open or in use, along with the programs using them. The options filter the output for specific types of connections and display them in an easily understandable format.

10. **`nmap -Pn <serverIP>`**: This command scans a target server for open ports, identifying what network services are running. It's crucial for security assessments, helping to uncover potentially vulnerable points of entry.

11. **`tcpdump icmp -i ens160`**: Captures and displays ICMP (Internet Control Message Protocol) packets, such as ping requests, on a specified network interface. It's useful for troubleshooting network connectivity issues.

12. **`logger -p authpriv.warning "Message"`**: Generates a log message with a specified priority. This tool is handy for testing how system logging processes custom messages, which can be critical for auditing or debugging.

13. **`systemctl restart rsyslog`**: Restarts the rsyslog service, ensuring that any changes to log configurations are applied. This is necessary after modifying log settings or files to ensure logs are correctly processed and stored.

14. **`logresolve < /var/log/httpd/access_log > output_file`**: Converts IP addresses in Apache's access logs to hostnames, making the logs easier to read and interpret. This can be important for understanding web traffic sources.

15. **`swatch -c /etc/swatch/config -t /var/log/secure`**: Monitors specified log files for patterns defined in the configuration file, alerting administrators to potential security issues or important events in real time.

16. **General Monitoring Tools (`df`, `du`, `top`, `ps`, `iostat`, `free`, `vmstat`, `sar`)**: These commands provide a wide range of system monitoring capabilities, from disk space and usage (`df`, `du`), to current processes and system load (`top`, `ps`), to detailed input/output statistics (`iostat`), memory usage (`free`), and overall system performance (`vmstat`, `sar`). Each tool offers a unique perspective on the system's state, allowing for comprehensive monitoring and troubleshooting.

# User Authentication & Pluggable Authentication Modules (PAM)

Here's a concise guide to the essential commands and concepts from the document on User Authentication and PAM:

1. **Understanding Password Storage**:
   - Linux stores user passwords using hash values in `/etc/shadow`.

2. **Using `pam_nologin`**:
   - `touch /etc/nologin` prevents non-root users from logging in.

3. **Allowing Passwordless Access**:
   - Add `auth sufficient pam_permit.so` to `/etc/pam.d/login` for passwordless access, for debugging or testing.

4. **Controlling Access with `pam_listfile`**:
   - Restrict vsftpd service access by editing `/etc/pam.d/vsftpd` with `auth required pam_listfile.so`.

5. **Tracking Login Attempts with `pam_faillock`**:
   - Configure faillock in `/etc/pam.d/system-auth` and `/etc/pam.d/password-auth` to lock accounts after failed login attempts.

6. **Time-based Access Restrictions**:
   - Use `pam_time.so` in `/etc/pam.d/vsftpd` and configure `/etc/security/time.conf` to restrict service access based on time.

7. **Configuring sudo for Specific Tasks**:
   - Use `visudo` to grant specific sudo privileges, like managing the Apache server, without full root access.



- **`chage`**: Manage password expiry and aging information, useful for enforcing password policies.
- **`passwd`**: Change user passwords, triggering PAM modules.
- **`faillog`**: Display or reset faillog entries, controlling user login failures.
- **`pam_tally2`**: Monitor and manage login attempt counts, useful for locking accounts after too many failed attempts.
- **`pam_cracklib.so`**: Enforce password complexity rules.
- **`pam_access.so`**: Control access to the system based on rules defined in `/etc/security/access.conf`.
- **`pam_wheel.so`**: Restrict `su` command usage to users in the wheel group.

