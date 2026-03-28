Small Office Network Design & Security (ALL-SMILE-DENTAL NETWORK West Seattle)
📌 Overview

This project demonstrates the design and implementation of a small office network with segmentation, routing, and security. The network connects two office locations using Layer 3 switching, routing, and firewall integration.

🎯 Objectives
Design a scalable small office network
Implement VLAN segmentation
Configure inter-VLAN routing using Layer 3 switches
Enable communication between two sites
Secure the network using a firewall
🏗️ Network Architecture
🔹 Site A (Left Side)
Network: 192.168.1.0/26
VLANs:
VLAN 10 → 192.168.1.0/26
VLAN 20 → 192.168.1.64/26
VLAN 30 → 192.168.1.128/26


Devices:
L2 switches for access layer
L3 switch for routing
🔹 Site B (Right Side)
Network: 192.168.2.0/26
Similar VLAN segmentation and design
🔹 WAN Connectivity
L3 Switch ↔ Router: 10.0.1.0/30
Router ↔ Router: 10.0.4.0/30
Router ↔ L3 Switch: 10.0.2.0/30
⚙️ Technologies Used
Cisco Layer 2 Switches (2960)
Cisco Layer 3 Switch (3560)
Cisco Routers (2911)
Cisco ASA Firewall (5505)
OSPF (Dynamic Routing)
VLANs & Trunking
NAT & ACLs (Firewall Security)
Packet Tracer  (Lab Environment)
🔧 Key Configurations
✅ VLAN Segmentation
Created VLANs to separate departments
Improved network organization and security
vlan 10
vlan 20
vlan 30
✅ Trunk Links
Configured trunk ports between L2 and L3 switches
interface fa0/1
switchport mode trunk
✅ Inter-VLAN Routing (L3 Switch)
ip routing

interface vlan 10
ip address 192.168.1.1 255.255.255.192
✅ OSPF Routing
router ospf 1
network 192.168.1.0 0.0.0.63 area 0
network 10.0.1.0 0.0.0.3 area 0
🔐 Firewall (Cisco ASA)
Placed between internal network and router
Configured:
Inside/Outside interfaces
NAT for internet access
ACLs for traffic filtering
object network LAN
subnet 192.168.1.0 255.255.255.0
nat (inside,outside) dynamic interface 

🔍 Testing & Verification
Verified VLAN connectivity using ping
Confirmed OSPF neighbors:
show ip ospf neighbor
Checked routing table:
show ip route

🚀 Results
Successful communication between:
VLANs (inter-VLAN routing)
Site A and Site B (via OSPF)
Network secured using firewall policies
Stable and scalable architecture achieved
📸 Screenshots

NETWORK TOPOLOGY

<img width="811" height="293" alt="image" src="https://github.com/user-attachments/assets/08d9ca5b-980d-4505-a928-3c0b33b6cb50" />
<img width="761" height="145" alt="Screenshot 2026-03-28 150002" src="https://github.com/user-attachments/assets/0d28f09e-ab41-4965-9818-c7c7bcba3fae" />
<img width="698" height="158" alt="Screenshot 2026-03-28 150023" src="https://github.com/user-attachments/assets/ba9a4340-68c8-4ef4-89bd-03a6f7605bf1" />
<img width="756" height="167" alt="Screenshot 2026-03-28 150113" src="https://github.com/user-attachments/assets/4887f1eb-6631-446a-92a3-b2131e2fd3d9" />
<img width="713" height="131" alt="Screenshot 2026-03-28 150357" src="https://github.com/user-attachments/assets/599d2bad-85f1-44c6-a5aa-f90656f7ebf1" />
<img width="692" height="121" alt="Screenshot 2026-03-28 150406" src="https://github.com/user-attachments/assets/3f4fc324-8ad5-4769-a30c-084e745494d4" />



📈 Future Improvements
Implement Site-to-Site VPN between offices
Integrate Wazuh SIEM for monitoring
Add IDS/IPS (Snort or Suricata)
Configure remote access VPN
💡 Skills Demonstrated
Network Design & Architecture
Routing & Switching (CCNA Level)
Network Security (Firewall, NAT, ACLs)
Troubleshooting & Debugging
GNS3 Lab Simulation
👤 Author

Abdi Malik
 Network/ Security Engineer
