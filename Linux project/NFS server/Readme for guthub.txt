# Linux NIS Server Setup Project

This project demonstrates the complete setup and configuration of an NIS (Network Information Service) server on a RHEL-based Linux environment, along with NFS for home directory sharing to a client machine.

## 🧰 Environment
- RHEL/CentOS based virtual machines
- One Server and One Client machine
- Root access required

## 🔧 Server Configuration Steps

1. **Rename the server VM:**
   ```bash
   hostnamectl set-hostname server
Check LAN card and IP address:

bash
Copy
Edit
ifconfig
Create user directories and users:

bash
Copy
Edit
mkdir /india
useradd -d /india/ranveer ranveer
passwd ranveer
useradd -d /india/ranvijay ranvijay
passwd ranvijay
Set NIS Domain:

bash
Copy
Edit
nisdomainname rhce
Configure /etc/sysconfig/network:

ini
Copy
Edit
NETWORKING=yes
HOSTNAME=server
NISDOMAIN=rhce
Install NIS packages:

bash
Copy
Edit
yum install ypserv ypbind -y
Start and enable NIS service:

bash
Copy
Edit
systemctl start ypserv
systemctl enable ypserv
Stop and disable firewall (for testing purposes only):

bash
Copy
Edit
systemctl stop firewalld
systemctl disable firewalld
Initialize NIS server:

bash
Copy
Edit
/usr/lib64/yp/ypinit -m
Install and configure NFS:

bash
Copy
Edit
yum install nfs-utils -y
echo "/india *(rw,sync,no_root_squash)" >> /etc/exports
systemctl start nfs-server
systemctl enable nfs-server
exportfs -a
🖥️ Client Configuration Steps
Check network and assign IP if needed:

bash
Copy
Edit
ifconfig
Set NIS domain and host:

bash
Copy
Edit
nisdomainname rhce
echo "server" >> /etc/hosts   # Or add server IP
Disable SELinux temporarily:

bash
Copy
Edit
setenforce 0
sed -i 's/SELINUX=enforcing/SELINUX=disabled/' /etc/selinux/config
Restart the client:

bash
Copy
Edit
reboot
Login using NIS user:

Successfully logged in with ranveer or ranvijay credentials from the server.

✅ Outcome
NIS server successfully authenticated users on the client.

NFS ensured home directories were available on client machine.

Demonstrated understanding of identity management and directory sharing in Linux.

📚 Skills Practiced
NIS Server Setup

NFS Configuration

User and Directory Management

SELinux and Firewall Handling

Network Configuration