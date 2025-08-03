✅ Today I successfully completed a hands-on networking project on BGP (Border Gateway Protocol) configuration as part of my CCNA practice.

🔹 Designed a CCNA network topology with 3 routers, 3 switches, and 12 PCs.

🔹 Attached WIC-1T serial ports to all three routers to establish WAN links.

🔹 Connected:
  - Router 1 (Serial 0/2/0) to Router 2 (Serial 0/2/0) using DCE and DTE connectors.
  - Router 2 (Serial 0/3/0) to Router 3 (Serial 0/2/0) similarly.

🔹 Connected:
  - Router 1 FastEthernet 0/0 to Switch 1 FastEthernet 0/1 using straight-through cable.
  - Linked 4 PCs to Switch 1, 4 to Switch 2, and 4 to Switch 3.

🔹 Used show ip interface brief to verify interfaces on Router 1.

🔹 Entered configuration mode and assigned:
  - Serial 0/2/0 → IP: 20.0.0.1 /8, set clock rate 64000, bandwidth 64, and brought the interface up using no shutdown.
  - FastEthernet 0/0 → IP: 10.0.0.1 /8, then enabled it.

🔹 On Router 2:
  - Configured Serial 0/2/0 → 20.0.0.2 /8
  - FastEthernet 0/0 → 30.0.0.1 /8
  - Serial 0/3/0 → 40.0.0.1 /8 with clock rate 64000 and bandwidth 64.

🔹 On Router 3:
  - Configured Serial 0/2/0 → 40.0.0.2 /8
  - FastEthernet 0/0 → 50.0.0.1 /8

🔹 Used the ping command from all connected PCs to test end-to-end connectivity across the network – ✅ successful!

🔄 BGP Configuration
📍 Router 1 (AS 10)

nginx
Copy
Edit
router bgp 10  
network 10.0.0.0  
network 20.0.0.0  
neighbor 20.0.0.2 remote-as 20  
📍 Router 2 (AS 20)

nginx
Copy
Edit
router bgp 20  
network 20.0.0.0  
network 30.0.0.0  
network 40.0.0.0  
neighbor 10.0.0.1 remote-as 10  
neighbor 40.0.0.2 remote-as 30  
📍 Router 3 (AS 30)

nginx
Copy
Edit
router bgp 30  
network 40.0.0.0  
network 50.0.0.0  
neighbor 40.0.0.1 remote-as 20  
✅ Final step: Used ping from each PC to validate BGP routing and reachability across all subnets – successfully verified.

💡 Skills Applied:
Routing protocols, BGP configuration, serial interface setup, IP addressing, interface troubleshooting, CCNA lab practice.

