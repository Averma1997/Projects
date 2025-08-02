🧠 CCNA Lab: EIGRP Protocol Configuration with 3 Routers, 3 Switches, and 12 PCs
This lab demonstrates how to configure EIGRP (Enhanced Interior Gateway Routing Protocol) in a network topology consisting of 3 routers, 3 switches, and 12 PCs, with proper IP addressing, interface setup, cable connections, and routing configuration.

🖼️ Network Topology
Routers: 3

Switches: 3

End Devices (PCs): 12

Cabling:

Serial connections between routers using WIC-1T modules (DCE/DTE).

Straight-through cables from routers to switches and switches to PCs.

🔌 Physical Setup
WIC-1T serial interfaces attached to all 3 routers.

Serial Cable Connections:

Router1 Serial0/2/0 (DCE) → Router2 Serial0/3/0 (DTE)

Router2 Serial0/3/0 (DCE) → Router3 Serial0/2/0 (DTE)

Straight-through Cable Connections:

Router1 FastEthernet0/0 → Switch1 FastEthernet0/1

Switch1 connected to 4 PCs.

Similarly, Router2 and Router3 connected to their respective switches and PCs.

⚙️ Router Configuration Steps
Router1
bash
Copy
Edit
show ip interface brief
configure terminal
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
Router2
bash
Copy
Edit
show ip interface brief
configure terminal
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
Router3
bash
Copy
Edit
show ip interface brief
configure terminal
interface serial 0/2/0
ip address 40.0.0.2 255.0.0.0
no shutdown
exit

interface fastethernet 0/0
ip address 50.0.0.1 255.0.0.0
no shutdown
exit

show ip interface brief
🧪 Connectivity Test
Used ping from each router to connected PCs.

All pings were successful from all routers (Router1, Router2, Router3).

🔁 EIGRP Routing Configuration
Router1
bash
Copy
Edit
show ip route
configure terminal
router eigrp 1
network 10.0.0.0
network 20.0.0.0
network 30.0.0.0
network 40.0.0.0
network 50.0.0.0
exit
Router2
bash
Copy
Edit
show ip route
configure terminal
router eigrp 1
network 10.0.0.0
network 20.0.0.0
network 30.0.0.0
network 40.0.0.0
network 50.0.0.0
exit
Router3
bash
Copy
Edit
show ip route
configure terminal
router eigrp 1
network 10.0.0.0
network 20.0.0.0
network 30.0.0.0
network 40.0.0.0
network 50.0.0.0
exit
✅ Final Testing
From Router1, pinged all network segments: 10.0.0.0, 20.0.0.0, 30.0.0.0, 40.0.0.0, 50.0.0.0.

Successfully pinged all 12 PCs from Router1.

Confirmed EIGRP routing tables on all routers.

📘 Summary
This lab covered:

Serial and Ethernet interface setup

IP addressing and connectivity validation

EIGRP routing configuration across all routers

End-to-end connectivity verification

🔗 This project is part of my CCNA hands-on training and helps solidify foundational networking concepts using Cisco IOS commands and routing protocols.