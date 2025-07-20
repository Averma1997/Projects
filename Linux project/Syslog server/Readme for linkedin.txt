🚀 Successfully completed an RSyslog Server & Client configuration project on Linux.

🔹 Used two Linux virtual machines for this setup.
🔹 Renamed the first machine to client using hostnamectl set-hostname.
🔹 Verified the network interface and IP address via ifconfig.
🔹 Installed RSyslog using the yum package manager.
🔹 Edited /etc/rsyslog.conf using vim and enabled four modules to support TCP/UDP traffic.
🔹 Started and enabled the RSyslog service using systemctl, and allowed TCP/UDP in the firewall.

🔹 Switched to the second VM and renamed it to server.
🔹 Checked IP address and ensured network connectivity via ping to the client machine.
🔹 Configured the RSyslog server in /etc/rsyslog.conf to receive logs:

mail.* @100.100.100.1

httpd.* @100.100.100.1

*.* @100.100.100.1
🔹 Restarted and enabled RSyslog service, opened required ports in firewall.

🔹 On the client machine, created users sonu, rohit and group G20.
🔹 On the server machine, verified log entries in /var/log/secure—logging was successful ✅

📌 Hands-on learning in Linux log management, service configuration, and system networking.