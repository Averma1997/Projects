RIP Protocol Configuration in CCNA Network (Lab Practice)
This project demonstrates the configuration of the RIP (Routing Information Protocol) in a CCNA-level simulated network using 3 routers, 3 switches, and 12 PCs. The entire network was built and configured in Cisco Packet Tracer.

🧱 Network Topology Overview
3 Routers with WIC-1T serial interfaces

3 Switches

12 PCs (4 connected to each switch)

Inter-router connections made using serial DCE/DTE cables

End devices connected using straight-through Ethernet cables

🔌 Physical Setup
Router Connections:

Connected Serial 0/2/0 (DCE) on Router 1 to Serial 0/3/0 (DTE) on Router 2

Connected Serial 0/3/0 (DCE) on Router 2 to Serial 0/2/0 (DTE) on Router 3

Switch and PC Connections:

Connected FastEthernet 0/0 of each router to the respective switch (FastEthernet 0/1)

Connected 4 PCs to each switch using straight-through cables

⚙️ Router Configurations
🚦 Router 1 (R1)
bash
Copy
Edit
enable
configure terminal
hostname R1
interface serial 0/2/0
ip address 20.0.0.1 255.0.0.0
clock rate 64000
bandwidth 64
no shutdown
exit
interface fastethernet 0/0
ip address 10.0.0.1 255.0.0.0
no shutdown
exit
show ip interface brief
🚦 Router 2 (R2)
bash
Copy
Edit
enable
show ip interface brief
configure terminal
hostname R2
interface serial 0/2/0
ip address 20.0.0.2 255.0.0.0
no shutdown
exit
interface fastethernet 0/0
ip address 30.0.0.1 255.0.0.0
no shutdown
exit
interface serial 0/3/0
ip address 40.0.0.1 255.0.0.0
clock rate 64000
bandwidth 64
no shutdown
exit
show ip interface brief
🚦 Router 3 (R3)
bash
Copy
Edit
enable
show ip interface brief
configure terminal
hostname R3
interface serial 0/2/0
ip address 40.0.0.2 255.0.0.0
no shutdown
exit
interface fastethernet 0/0
ip address 50.0.0.1 255.0.0.0
no shutdown
exit
show ip interface brief
🖥️ PC Configurations
Each PC was manually assigned:

A unique IP address

Subnet mask

Default gateway (IP of connected router interface)

All PCs were tested using ping to verify connectivity. All tests were successful.

🛰️ RIP Routing Configuration
✅ R1 - RIP Setup
bash
Copy
Edit
router rip
network 10.0.0.0
network 20.0.0.0
network 30.0.0.0
network 40.0.0.0
network 50.0.0.0
exit
show ip route
✅ R2 - RIP Setup
bash
Copy
Edit
router rip
network 10.0.0.0
network 20.0.0.0
network 30.0.0.0
network 40.0.0.0
network 50.0.0.0
exit
show ip route
✅ R3 - RIP Setup
bash
Copy
Edit
router rip
network 10.0.0.0
network 20.0.0.0
network 30.0.0.0
network 40.0.0.0
network 50.0.0.0
exit
show ip route
✅ Final Verification
Performed ping tests from Router 1 to PCs across all networks.

All connectivity tests passed successfully, confirming proper RIP routing between routers.

📚 Summary
This lab exercise involved configuring a full mesh topology with RIP version 1 routing on three Cisco routers and testing full network connectivity using static IP addressing and ping tests.

🧠 Skills Practiced: Static IP assignment, Router interface configuration, RIP setup, Serial & Ethernet cabling, Connectivity testing.

