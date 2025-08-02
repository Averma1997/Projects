🚀 Successfully Configured EIGRP Protocol in My CCNA Lab (3 Routers, 3 Switches, 12 PCs) 💻🖧

Today, I completed a practical EIGRP (Enhanced Interior Gateway Routing Protocol) setup as part of my CCNA networking practice. Here's a step-by-step breakdown of the lab:

✅ Network Topology:

3 Routers

3 Switches

12 PCs

🖥️ Hardware Configuration:

Attached WIC-1T serial ports to all three routers.

Connected DCE connector to Router1’s Serial0/2/0, and DTE connector to Router2’s Serial0/3/0.

Another DCE connector from Router2’s Serial0/3/0 to Router3’s Serial0/2/0.

📡 Straight-through cable connections:

Connected FastEthernet0/0 of Router1 to FastEthernet0/1 of Switch1.

Connected 4 PCs to each switch using straight-through cables.

🔧 Router Configurations:

📍 Router1:

Verified interfaces with show ip interface brief

Assigned IPs:

Serial0/2/0 → 20.0.0.1 255.0.0.0 (with clock rate 64000 and bandwidth 64)

FastEthernet0/0 → 10.0.0.1 255.0.0.0

Used no shutdown on all interfaces

📍 Router2:

Serial0/2/0 → 20.0.0.2 255.0.0.0

FastEthernet0/0 → 30.0.0.1 255.0.0.0

Serial0/3/0 → 40.0.0.1 255.0.0.0 (with clock rate 64000 and bandwidth 64)

Verified all with show ip interface brief

📍 Router3:

Serial0/2/0 → 40.0.0.2 255.0.0.0

FastEthernet0/0 → 50.0.0.1 255.0.0.0

Verified all interfaces are up

📡 Ping Test:

Successfully pinged from Router1 to all directly connected PCs and networks

Repeated the same on Router2 and Router3 — all successful!

🧠 EIGRP Configuration:

Verified routing table with show ip route

Enabled EIGRP on all routers:

router eigrp 1

network 10.0.0.0

network 20.0.0.0

network 30.0.0.0

network 40.0.0.0

network 50.0.0.0

📍 Final Testing:

From Router1, pinged all networks (10, 20, 30, 40, 50) and all 12 PCs — ✅ all successful.

💡 This hands-on lab helped me understand real-world EIGRP configuration, IP addressing, interface status checks, and end-to-end connectivity testing.

#CCNA #Networking #EIGRP #Cisco #RouterConfiguration #PracticalLearning #IPRouting #LabSetup #ITSkills