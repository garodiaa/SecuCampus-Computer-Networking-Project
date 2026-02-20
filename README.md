# SecuCampus

![Version](https://img.shields.io/badge/version-1.0.0-283593?style=flat)
![Cisco](https://img.shields.io/badge/Simulator-Cisco%20Packet%20Tracer-1E88E5?logo=cisco&logoColor=white&style=flat)
![VLAN](https://img.shields.io/badge/Networking-VLAN%20%7C%20RIPv2-00897B?style=flat)
![WAN](https://img.shields.io/badge/WAN-Serial%20Links-6D4C41?style=flat)
![License](https://img.shields.io/badge/License-Academic-4CAF50?style=flat)

## University campus network design and simulation using Cisco Packet Tracer.

### Overview

SecuCampus is a Computer Networking Lab project that models a secure, segmented, and scalable multi-campus network. Using Cisco Packet Tracer, the design links a main campus (DSC) and a branch campus, implements VLAN-based departments, provisions DHCP per subnet, runs RIPv2 for inter-building routing, and maintains WAN links for external access.

### Academic Objective

- enforce logical isolation through VLAN segmentation
- enable inter-VLAN routing via router-on-a-stick
- provision subnet-specific DHCP services
- run RIPv2 for dynamic campus routing
- configure static routes for external resources
- simulate WAN serial connectivity in a hierarchical layout

### Network Snapshot

![SecuCampus topology](SecuCampus_image.png)

### Main Campus (DSC)

| VLAN ID | Department     | Subnet           |
| --- | --- | --- |
| 10  | Admin          | 192.168.1.0/24 |
| 20  | HR             | 192.168.2.0/24 |
| 30  | Accounts       | 192.168.3.0/24 |
| 40  | Admission      | 192.168.4.0/24 |
| 50  | FSIT Faculty   | 192.168.5.0/24 |
| 60  | FBE Faculty    | 192.168.6.0/24 |
| 70  | Computer Lab   | 192.168.7.0/24 |
| 80  | IT Room (FTP)  | 192.168.8.0/24 |

### Branch Campus

| VLAN ID | Department   |
| --- | --- |
| 90  | Staff Room  |
| 100 | Student Lab |

Branch connectivity relies on WAN serial links back to DSC.

### WAN Links

| Link | Subnet |
| --- | --- |
| DSC ↔ Branch | 10.10.10.0/30 |
| DSC ↔ ISP    | 10.10.10.4/30 |

### Technologies & Concepts

- Cisco Packet Tracer, routers, and switches
- VLAN tagging (802.1Q)
- Router-on-a-stick inter-VLAN routing
- DHCP pools per subnet
- RIPv2 dynamic routing
- Static routes for ISP/cloud services
- FTP server configuration inside IT VLAN
- Serial WAN link simulation and hierarchical design

### Security & Segmentation

- VLAN isolation per department
- dedicated subnets for each functional area
- controlled routing between VLANs
- isolated IT room hosting FTP services
- structured WAN paths to guard campus borders

### Routing Strategy

- **RIPv2** handles communication between DSC and branch, auto-updating routes.
- **Static routes** guarantee deterministic access to external resources (e.g., hosted email/FTP).

### Repository Layout

```
SecuCampus---Computer-Networking-Project/
├── SecuCampus.pkt           # Packet Tracer topology
├── SecuCampus_image.png     # Network diagram
├── img.png                  # Auxiliary visuals
└── Command Files/
	├── command_router.txt   # Router CLI configs
	├── command_switch.txt   # VLAN & switch configurations
	└── command_server.txt   # FTP/server settings
```

### How to Run

1. Install Cisco Packet Tracer (v7+ recommended).
2. Open `SecuCampus.pkt`.
3. Validate connectivity using `ping`, FTP commands, and `show ip route`.
4. Modify VLANs or routing tables to test scalability scenarios.

### Design Philosophy

SecuCampus follows a hierarchical model:

- **Access Layer**: end devices and VLAN assignment
- **Distribution Layer**: routing, ACLs, and segmentation
- **Core Layer**: WAN serial connectivity and ISP handoff

### Project Outcome

- inter-department VLAN communication with controlled routing
- seamless branch-to-main campus connectivity
- automatic IP address allocation per subnet
- secure FTP access inside the IT VLAN
- scalable topology ready for future departments

### Learning Outcome

- practical exposure to enterprise network design
- hands-on VLAN and routing protocol configuration
- WAN link simulation with Cisco CLI
- troubleshooting multi-campus networks in Packet Tracer

SecuCampus bridges theoretical networking coursework with real-world Cisco implementations.
