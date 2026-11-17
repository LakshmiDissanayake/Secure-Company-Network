# Advanced Enterprise Networking Project #
### Design and Implementation of a Secure Company Network System

A secure, redundant, and scalable enterprise network designed for **Cytonn Innovation Ltd** - a 600-user company moving to a new 3-floor building.

Built using **Cisco Packet Tracer**.

## Project Overview

Cytonn Innovation Ltd required a new network for its new building with top-tier performance, redundancy, scalability, and security.

The design implements a **Hierarchical 3-Layer Model** with firewall security zones, dual ISPs, and centralized wireless management.

**Departments Covered:** Sales & Marketing, Human Resources, Logistics, Finance & Accounts, Admin & PR, ICT, and Server Room.
**ICT Team:** Software Developers, Cloud Engineers, Cybersecurity Engineers, Network Engineers, System Admins, IT Support, Business Analysts, Project Managers.

## Network Topology

* **Core Layer:** 2x Catalyst 3850 48-Port Multilayer Switches (Redundant)
* **Access Layer:** Catalyst 2960 48-Port Switches
* **Security:** 2x Cisco ASA 5500-X Firewalls
* **Wireless:** Cisco Wireless LAN Controller (WLC) + Lightweight Access Points (LAPs)
* **Voice:** Cisco Voice Gateway Router + IP Phones
* **Servers:** 2x Physical Servers for Virtualization

## Firewall Security Zones (ASA)

| Zone | Security Level | Devices |
| :--- | :--- | :--- |
| Inside | High (100) | AD, DHCP, DNS, RADIUS, LAN Users |
| DMZ | Medium (50) | FTP, WEB, Email, APP, NAS Storage |
| Outside | Low (0) | ISPs - SEACOM & Safaricom |

## IP Addressing Plan

| Network | IP Range | Purpose |
| :--- | :--- | :--- |
| Management | 192.168.10.0/24 | Device Management |
| LAN | 172.16.0.0/16 | Wired LAN Users |
| WLAN | 10.20.0.0/16 | Wireless Users |
| VoIP | 172.30.0.0/16 | IP Phones |
| DMZ | 10.11.11.0/27 | DMZ Servers |
| Public - SEACOM | 105.100.50.0/30 | ISP 1 |
| Public - Safaricom | 197.200.100.0/30 | ISP 2 |

## VLAN Configuration

| VLAN ID | Name | Purpose |
| :--- | :--- | :--- |
| 10 | Management | Management |
| 20 | LAN | Wired LAN |
| 50 | WLAN | Wireless |
| 70 | VoIP | Voice |
| 199 | Blackhole | Unused Ports (Security) |

All unused ports are assigned to VLAN 199 Blackhole.

## Key Features Implemented

1. Hierarchical Design with Redundancy
2. Dual ISP Connectivity - SEACOM & Safaricom for failover
3. Cisco ASA Firewall - Inside / DMZ / Outside Zones, Security Levels, Static Routes
4. Inter-VLAN Routing on Multilayer Core Switch
5. OSPF as Routing Protocol on Firewall, Routers & Multilayer Switches
6. HSRP for High Availability, Load Balancing & Failover
7. EtherChannel (LACP) for Link Aggregation
8. STP PortFast + BPDUguard for Fast Convergence & Loop Protection
9. DHCP Server - Dynamic IP for all end devices
10. WLC + LAPs - Centralized WiFi for Employees, Corporate Users, Auditors & Guests
11. VoIP - Configured on Voice Gateway, Dial Numbers in 4... format
12. Standard ACL for SSH - Remote access only allowed for Senior Network Security Engineer PC
13. Basic Hardening - Hostnames, Console/Enable Passwords, Banner MOTD, Password Encryption, no ip domain-lookup
14. Static Addressing for Server Room Devices
15. Subnetting for efficient IP allocation

## Testing & Verification

Verified with:
* ping - Inter-department, DMZ Server, and Internet connectivity
* show ip ospf neighbor - OSPF adjacency
* show standby brief - HSRP Active/Standby status
* show vlan brief - VLAN assignment
* show etherchannel summary - LACP status
* IP Phone to IP Phone calls
* DHCP ipconfig on client PCs
  
[Download Secure-Company-Network](Secure-Company-Network.pkt)

[View Screenshot Folder](Screenshot/)

## Tools Used

* Cisco Packet Tracer
* Cisco ASA 5500-X Firewall
* Cisco Catalyst 3850 & 2960 Switches
* Cisco WLC & LAPs
* Cisco IP Phones

