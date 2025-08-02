🌐 Apache Web Server Setup on RHEL Linux
This project demonstrates how to install and configure an Apache Web Server on Red Hat Enterprise Linux (RHEL) with custom virtual hosts and port security enhancement.

📌 Steps Performed
1. Check Network and YUM Repository
bash
Copy
Edit
ifconfig             # Check network interface and IP address  
yum repolist         # Verify YUM repositories
2. Configure Hostname Resolution
bash
Copy
Edit
vim /etc/hosts       # Edit hosts file to resolve local server names
3. Test Network Connectivity
bash
Copy
Edit
ping google.com             # Check internet access  
ping <server-ip>            # Verify server IP reachability  
ping <server-name>          # Verify hostname resolution
4. Install Apache HTTP Server
bash
Copy
Edit
yum install httpd           # Install Apache web server
5. Start and Enable Apache Service
bash
Copy
Edit
systemctl start httpd       # Start Apache daemon  
systemctl enable httpd      # Enable it at boot
6. Allow HTTP Traffic in Firewall
bash
Copy
Edit
firewall-cmd --permanent --add-service=http  
firewall-cmd --reload
7. Create Homepage
Navigate to the default document root:

bash
Copy
Edit
cd /var/www/html/
Create and edit the homepage:

bash
Copy
Edit
vim index.html
Insert the following content:

html
Copy
Edit
<html>
  <title> Thank you so much </title>
  <body>
    <marquee> Welcome to all of you on my Apache server "Awesome Verma" </marquee>
  </body>
</html>
8. Restart Apache Service
bash
Copy
Edit
systemctl restart httpd
9. Access Web Page
Open Firefox or browser:

cpp
Copy
Edit
http://<your-server-ip>
📁 Configure Virtual Hosts
10. Create Custom Directories
bash
Copy
Edit
mkdir /var/www/google  
mkdir /var/www/yahoo
11. Add Web Page Files
bash
Copy
Edit
echo "This is my local web page" > /var/www/google/google.html  
echo "This is my local web page" > /var/www/yahoo/yahoo.html

cat /var/www/google/google.html  
cat /var/www/yahoo/yahoo.html
12. Edit Apache Configuration
Edit the virtual host configuration:

bash
Copy
Edit
vim /etc/httpd/conf/httpd.conf
Add the following blocks:

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
13. Add Host Entries
bash
Copy
Edit
vim /etc/hosts
Add:

Copy
Edit
100.100.100.2   google.example.com yahoo.example.com
14. Restart Apache and Test Virtual Hosts
bash
Copy
Edit
systemctl restart httpd
Access the sites:

http://google.example.com

http://yahoo.example.com

🔐 Change Default Port (Optional Security Enhancement)
15. Change Apache Port
Edit the config file:

bash
Copy
Edit
vim /etc/httpd/conf/httpd.conf
Change the Listen directive:

mathematica
Copy
Edit
Listen 82
16. Allow New Port via SELinux
bash
Copy
Edit
semanage port -a -t http_port_t -p tcp 82
17. Restart and Access via Port 82
bash
Copy
Edit
systemctl restart httpd
Access site:

cpp
Copy
Edit
http://<your-server-ip>:82
✅ Result
Successfully configured:

Apache Web Server

Custom homepage

Multiple name-based virtual hosts

Port security (port changed from 80 to 82)

🛠️ Tools & Technologies
Red Hat Enterprise Linux (RHEL)

Apache HTTP Server

SELinux

FirewallD

YUM package manager

Virtual Hosting

