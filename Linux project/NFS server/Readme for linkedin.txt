✅ LinkedIn Post (Line-wise, professional tone):
Today I completed a hands-on Linux project on setting up an NIS (Network Information Service) Server.

🔹 Renamed the virtual machine to server and checked the LAN card using ifconfig to verify IP assignment.
🔹 Created a directory named india using mkdir, and inside it, added two users ranveer and ranvijay with useradd, and assigned passwords.
🔹 Verified home directories were created for the users under india.
🔹 Assigned NIS domain name rhce using nisdomainname and updated /etc/sysconfig/network with:

ini
Copy
Edit
NETWORKING=yes  
HOSTNAME=server  
NISDOMAIN=rhce
🔹 Installed YP (NIS) packages using yum, started and enabled the ypserv service with systemctl.
🔹 Disabled firewall to allow NIS traffic.
🔹 Initialized NIS server using /usr/lib64/yp/ypinit -m.
🔹 Installed and configured NFS server for home directory sharing.
🔹 Started and enabled NFS service using systemctl.
🔹 Configured exports file for sharing directories.
🔹 Switched to the client machine, verified network configuration and IP.
🔹 Set the client to use the server for NIS authentication, disabled SELinux, and restarted the client.
🔹 Successfully logged in from the client using the NIS-managed users.

💡 Skills Covered: NIS Server, NFS, User Management, Network Configuration, SELinux, Firewall, YUM, Systemctl.
#Linux #NIS #SysAdmin #RHCE #Networking #NFS #OpenSource #LinuxProjects