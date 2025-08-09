✅ Today I completed a hands-on project on setting up an NFS (Network File System) Server in RHEL Linux.

🔹 Checked the LAN card IP address using the ifconfig command.
🔹 Listed existing files and directories using the ls command.
🔹 Created a new directory named vishesh and assigned full permissions using chmod 777.
🔹 Installed the NFS server package using the YUM package manager.
🔹 Configured the NFS exports file (/etc/exports) with the entry: /vishesh *(rw,sync).
🔹 Started the NFS server daemon using systemctl start nfs-server and enabled it for startup.
🔹 Allowed NFS-related traffic through the firewall using:
firewall-cmd --permanent --add-service=nfs --add-service=rpc-bind --add-service=mountd
🔹 Verified the shared exports using exportfs -v, showmount -e, and showmount -e 100.100.100.1.
🔹 On the client machine, checked the IP address using ifconfig and installed the NFS client package.
🔹 Created a directory named share and mounted the server directory using:
mount 100.100.100.1:/vishesh /share
🔹 Confirmed connectivity and mounted file system details using df -Th.
🔹 Created a test file in the shared directory from the client and verified it on the server—successful!

💡 Outcome: Successfully configured an NFS server-client setup in RHEL Linux for seamless file sharing across systems.