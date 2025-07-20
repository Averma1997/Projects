# RSyslog Server & Client Configuration on Linux

This project demonstrates how to configure an RSyslog server and client on two Linux virtual machines using `rsyslog`, firewall rules, and basic user/group management.

## 🛠️ Environment

- OS: CentOS/RHEL-based Linux VMs
- Tools: `rsyslog`, `firewalld`, `vim`, `systemctl`, `yum`

## 🔧 Step-by-Step Setup

### ✅ Client Machine (Log Sender)

1. **Set hostname:**
   ```bash
   hostnamectl set-hostname client
Check IP address:

bash
Copy
Edit
ifconfig
Install rsyslog:

bash
Copy
Edit
sudo yum install rsyslog -y
Configure /etc/rsyslog.conf:

Open file using vim

Enable the following modules (uncomment if needed):

lua
Copy
Edit
module(load="imudp")
input(type="imudp" port="514")
module(load="imtcp")
input(type="imtcp" port="514")
Start & enable service:

bash
Copy
Edit
sudo systemctl start rsyslog
sudo systemctl enable rsyslog
Allow firewall ports:

bash
Copy
Edit
firewall-cmd --permanent --add-port=514/udp
firewall-cmd --permanent --add-port=514/tcp
firewall-cmd --reload
✅ Server Machine (Log Receiver)
Set hostname:

bash
Copy
Edit
hostnamectl set-hostname server
Check IP address and connectivity:

bash
Copy
Edit
ifconfig
ping <client-IP>
Edit /etc/rsyslog.conf:
Add lines at the end:

graphql
Copy
Edit
mail.*    @100.100.100.1
httpd.*   @100.100.100.1
*.*       @100.100.100.1
Start & enable rsyslog:

bash
Copy
Edit
sudo systemctl restart rsyslog
sudo systemctl enable rsyslog
Allow firewall ports:

bash
Copy
Edit
firewall-cmd --permanent --add-port=514/udp
firewall-cmd --permanent --add-port=514/tcp
firewall-cmd --reload
✅ Final Verification
On Client:
Create users and group:

bash
Copy
Edit
sudo useradd sonu
sudo useradd rohit
sudo groupadd G20
On Server:
Check logs:

bash
Copy
Edit
cat /var/log/secure
If logs from the client appear here, your RSyslog setup is working correctly! ✅

📚 Skills Demonstrated
Linux System Administration

Network Troubleshooting

Centralized Log Management (RSyslog)

Firewall Configuration

User and Group Management

