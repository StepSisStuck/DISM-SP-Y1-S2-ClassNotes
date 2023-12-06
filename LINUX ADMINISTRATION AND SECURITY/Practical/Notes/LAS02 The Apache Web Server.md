# LAS02 The Apache Web Server

# Table of Contents

# Setting up a basic Apache web server
1. On the server, install the Apache web server package:
```bash
dnf -y install httpd
systemctl enable httpd
systemctl start httpd
```

2. Doing a quick check to see if the web server is running:
```bash
curl http://localhost | head -n 15
```

3. Start firefox and go to the URL http://localhost

4. Create a new file in the /var/www/html directory called index.html with the following contents:
```bash
curl https://localhost > /tmp/index.html
cp /tmp/index.html /var/www/html/index.html
```
As you can see, you have cloned the default web page to a new file called index.html in the /var/www/html directory. This is the default web page that is displayed when you go to the URL http://localhost.

5. Lets edit the file /var/www/html/index.html and change the title to "My First Web Page". You can use vi or nano to edit the file.
```bash
nano /var/www/html/index.html
```

6. Now reload the web page in firefox and you should see the new title.

7. Now, lets allow access to the web server from other computers on the network by adding a firewall rule:
```bash
firewall-cmd --add-service=http --permanent
firewall-cmd --reload
```

8. Now, log into client, and open firefox and go to the URL http://<<server IP>server IP>. You should see the web page.


9. To view the apache main configuration file:
```bash
cat /etc/httpd/conf/httpd.conf
```
Look in the `documentroot` or `directory index` section to see where the default web page is located.

10. Let's create a new directory in HTML directory
```bash
mkdir -p /var/www/html/books
```

11. Let's create a new file in the books directory called books.html with the following contents:

```bash
touch /var/www/html/books/books.html
```
```bash
sudo nano /var/www/html/books/books.html
```
```HTML
<html>
This is BookA
</html>
```

12. Now if you go to firefox on server
 http://localhost/books, should be able to see the content of books.html
    
Apache2 comes with an optional server-stauts module which can provide a monitor view of the server status. To enable this optional feature, insert the following near to the end of your apache server main config file (/etc/httpd/conf/httpd.conf), right before the 'Supplemental Configuration' section.


```bash
nano /etc/httpd/conf/httpd.conf
```
```bash
<Location /server-status>
    SetHandler server-status
    Require host localhost
</Location>
```


The above enables the virtual url of http://localhost/server-status and allows everyone from anywhere to access and view the current server status.
You need to restart the server using

```bash
systemctl restart httpd
```

13. Client side, open firefox and go to the URL http://<<server IP>server IP>/server-status. You should see the server status page.
    

14. Back on server 

Scaling up/down the server performance by changing the number of pre-loaded worker instances.
Edit the main config file /etc/httpd/conf/httpd.conf. After the DocumentRoot line, add a few lines to specify the number for StartServers , ThreadsPerChild , ServerLimit and MaxRequestWorkers.

```bash
nano /etc/httpd/conf/httpd.conf
```
```bash
<IfModule mpm_prefork_module>
    StartServers             5
    MinSpareServers          5
    MaxSpareServers         10
    MaxRequestWorkers      150
    MaxConnectionsPerChild   0
</IfModule>
```

Back on client, do you see the difference in the server status page? Try to refresh the page a few times and see if the number of busy workers changes.


15. Install the httpd-manual package:
```bash
dnf -y install httpd-manual
```
Basically you just downloaded the apache manual to your server.

16. Using your web browser, go to the URL file:///usr/share/httpd/manual/index.html. You should see the apache manual page.

17. When you enter http://localhost/books, a directory listing is displayed. This is because the directory index is not set. To set the directory index, edit the file /etc/httpd/conf/httpd.conf and add the following line:
```bash
nano /etc/httpd/conf/httpd.conf
```
```bash
<Directory /var/www/html/books>
    Options -Indexes
</Directory>
```
Reload the httpd service:
```bash
systemctl reload httpd
```
Now, if you go to http://localhost/books, you should see a 403 Forbidden error.

So you need to enter the full URL http://localhost/books/books.html to see the content of books.html.

## Basic Access Control
Edit the file /etc/httpd/conf/httpd.conf and add the following lines:
```bash
nano /etc/httpd/conf/httpd.conf
```
```bash
<Directory /var/www/html/books>
    Options -Indexes
    Require all denied
    Require <IP address of client>
</Directory>
```
Reload the httpd service:
```bash
systemctl reload httpd
```
Now, if you go to http://localhost/books, you should see a 403 Forbidden error.

But if you enter using client http://<<server IP>server IP>/books/books.html, you should be able to see the content of books.html.


## Securing Apache with SSL
1. Install the mod_ssl package:
```bash
dnf info mod_ssl
dnf -y install mod_ssl
```

2. The SSL module for Apache will generate a default ssl.conf file in the /etc/httpd/conf.d folder. In this ssl.conf configuration file, it will refer to the following two folders for the required Private key and Certificate for the https deployment.
For Private key: /etc/pki/tls/private/
For Certificate: /etc/pki/tls/certs/


