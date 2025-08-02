🚀 Project Completed: Apache Web Server Setup on RHEL Linux

Today, I successfully set up and configured an Apache web server on Red Hat Enterprise Linux (RHEL). Here's a step-by-step overview of the project:

1️⃣ First, I checked the IP address of the network interface using the ifconfig command.
2️⃣ Verified YUM repository status with yum repolist.
3️⃣ Edited the hosts file using vim /etc/hosts to configure hostname resolution.
4️⃣ Tested network connectivity using the ping command (to google.com, server IP, and server hostname).
5️⃣ Installed the Apache package using:

bash
Copy
Edit
yum install httpd
6️⃣ Started and enabled the Apache service using:

bash
Copy
Edit
systemctl start httpd  
systemctl enable httpd
7️⃣ Allowed HTTP traffic through the firewall.
8️⃣ Navigated to the default web root directory:

bash
Copy
Edit
cd /var/www/html/
9️⃣ Created and edited the index.html file using vim, with the following content:

html
Copy
Edit
<html>
<title> Thank you so much </title>
<body>
<marquee> Welcome to all of you on my Apache server "Awesome Verma" </marquee>
</body>
</html>
🔟 Restarted the Apache daemon to apply changes:

bash
Copy
Edit
systemctl restart httpd
🔁 Opened the browser and successfully accessed the webpage.

📁 Created subdirectories under /var/www/:

/var/www/google

/var/www/yahoo

📄 Inside each directory, created a basic HTML file using the echo command:

bash
Copy
Edit
echo "This is my local web page" > google.html  
echo "This is my local web page" > yahoo.html
🔍 Verified file content using cat.

🛠️ Configured name-based Virtual Hosting by editing /etc/httpd/conf/httpd.conf:

apache
Copy
Edit
<VirtualHost 100.100.100.2:80>
    ServerAdmin root@server1.example.com
    DocumentRoot /var/www/google
    DirectoryIndex google.html
    ServerName google.example.com
    ServerAlias googl.com
    CustomLog "logs/google_access_log" combined
    ErrorLog "logs/google_error_log"
</VirtualHost>

<VirtualHost 100.100.100.2:80>
    ServerAdmin root@server1.example.com
    DocumentRoot /var/www/yahoo
    DirectoryIndex yahoo.html
    ServerName yahoo.example.com
    ServerAlias yahoo.com
    CustomLog "logs/yahoo_access_log" combined
    ErrorLog "logs/yahoo_error_log"
</VirtualHost>
🖊️ Updated /etc/hosts with local entries for google.example.com and yahoo.example.com.

🌐 Accessed both virtual hosts successfully in the browser.

🔐 For security enhancement, changed the Apache listening port from 80 to 82 in httpd.conf.

🔓 Allowed new port via SELinux using:

bash
Copy
Edit
semanage port -a -t http_port_t -p tcp 82
✅ Restarted the Apache service and verified successful access on port 82.

📌 Technologies Used: Apache, RHEL, YUM, SELinux, Virtual Host, FirewallD
💡 Skills Gained: Web server setup, virtual hosting, port security, firewall & SELinux configuration.

#Linux #RHEL #ApacheServer #VirtualHost #DevOps #SystemAdministration #RedHat #Networking #LinuxAdmin #WebServer #ProjectCompletion