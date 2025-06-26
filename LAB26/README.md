<a name="top"></a>
![Timeline2_shutterstoc](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB26/image.png)

[![OS](https://img.shields.io/badge/OS-linux%2C%20windows%2C%20macOS-0078D4)]()
[![CPU](https://img.shields.io/badge/CPU-x86%2C%20x64%2C%20ARM%2C%20ARM64-FF8C00)]()
[![security rating](https://sonarcloud.io/api/project_badges/measure?project=Abblix_Oidc.Server&metric=security_rating)]()
[![reliability rating](https://sonarcloud.io/api/project_badges/measure?project=Abblix_Oidc.Server&metric=reliability_rating)]()
[![maintainability rating](https://sonarcloud.io/api/project_badges/measure?project=Abblix_Oidc.Server&metric=sqale_rating)]()
[![getting started](https://img.shields.io/badge/getting_started-guide-1D76DB)]()
[![Free](https://img.shields.io/badge/free_for_non_commercial_use-brightgreen)](#-license)

⭐ Star us on GitHub — it motivates us a lot!

[![Share](https://img.shields.io/badge/share-000000?logo=x&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-1877F2?logo=facebook&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-0A66C2?logo=linkedin&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-FF4500?logo=reddit&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-0088CC?logo=telegram&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)

# 💡 Network Topology
 - 2 Multilayer (L3) Switches
 - 1 Router
 - 1 Layer 2 Switch behind the router
 - L3SW1: should work as a Layer 2 switch only (no routing).
 - L3SW2: acts as both a Layer 3 router (for inter-VLAN routing) and a Layer 2 switch.
 - Each device uses different VLANs
 - Goal: End-to-end inter-VLAN communication (ping between networks
---
# ✅ Objective
Ensure devices in different VLANs and across all switches (even behind the router) can ping each other.

# 🧠 Key Concepts
- L3 Switches handle VLAN routing (SVI)
- Router used to reach external networks (inter-switch or access layer)
- Trunk ports carry VLANs between switches/router
- Routing protocols (or static routes) enable communication

# 🔹L3SW1 (Layer 2 Only)

``` bash
L3SW1> enable
L3SW1# configure terminal
L3SW1(config)# hostname L3SW1
L3SW1(config)# 
L3SW1(config)# vlan 10
L3SW1(config-vlan)# exit
L3SW1(config)# vlan 20
L3SW1(config-vlan)# exit
L3SW1(config)# 
L3SW1(config)# interface GigabitEthernet0/1
L3SW1(config-if)# switchport mode access
L3SW1(config-if)# switchport access vlan 10
L3SW1(config-if)# exit
L3SW1(config)# 
L3SW1(config)# interface GigabitEthernet0/2
L3SW1(config-if)# switchport mode access
L3SW1(config-if)# switchport access vlan 20
L3SW1(config-if)# exit
L3SW1(config)# 
L3SW1(config)# interface GigabitEthernet1/1
L3SW1(config-if)# description Uplink to L3SW2
L3SW1(config-if)# switchport mode trunk
L3SW1(config-if)# exit
L3SW1(config)# 
L3SW1(config)# no ip routing
L3SW1(config)# exit
L3SW1#
```
# 🔹 2. L3SW2 (Router + Switch)


``` bash
L3SW2> enable
L3SW2# configure terminal
Enter configuration commands, one per line.  End with CNTL/Z.
L3SW2(config)# hostname L3SW2
L3SW2(config)# ip routing
L3SW2(config)# 
L3SW2(config)# vlan 10
L3SW2(config-vlan)# exit
L3SW2(config)# vlan 20
L3SW2(config-vlan)# exit
L3SW2(config)# 
L3SW2(config)# interface Vlan10
L3SW2(config-if)# ip address 192.168.10.1 255.255.255.0
L3SW2(config-if)# no shutdown
L3SW2(config-if)# exit
L3SW2(config)# 
L3SW2(config)# interface Vlan20
L3SW2(config-if)# ip address 192.168.20.1 255.255.255.0
L3SW2(config-if)# no shutdown
L3SW2(config-if)# exit
L3SW2(config)# 
L3SW2(config)# interface GigabitEthernet1/1
L3SW2(config-if)# description Uplink from L3SW1
L3SW2(config-if)# switchport mode trunk
L3SW2(config-if)# exit
L3SW2(config)# 
L3SW2(config)# interface GigabitEthernet0/1
L3SW2(config-if)# switchport mode access
L3SW2(config-if)# switchport access vlan 10
L3SW2(config-if)# exit
L3SW2(config)# 
L3SW2(config)# interface GigabitEthernet0/2
L3SW2(config-if)# switchport mode access
L3SW2(config-if)# switchport access vlan 20
L3SW2(config-if)# exit
L3SW2(config)# 
L3SW2(config)# interface GigabitEthernet0/3
L3SW2(config-if)# description Connection to Router
L3SW2(config-if)# no switchport
L3SW2(config-if)# ip address 192.168.200.1 255.255.255.252
L3SW2(config-if)# no shutdown
L3SW2(config-if)# exit
L3SW2(config)# 
L3SW2(config)# ip route 0.0.0.0 0.0.0.0 192.168.200.2
L3SW2(config)# exit
L3SW2#

```
# 🔹 2. ROUTER CONFIGURATION (with Subinterfaces)

```bash
Router> enable
Router# configure terminal
!
interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
!
interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
!
interface GigabitEthernet0/0.30
 encapsulation dot1Q 30
 ip address 192.168.30.1 255.255.255.0
!
interface GigabitEthernet0/0
 no shutdown
!
exit

```

# 🔹 1. L2 SWITCH CONFIGURATION

```bash
Switch> enable
Switch# configure terminal
!
vlan 10
name HR
vlan 20
name IT
vlan 30
name Sales
!
interface range Gig0/1 - 3
 switchport mode access
 switchport access vlan 10
!
interface range Gig0/4 - 6
 switchport mode access
 switchport access vlan 20
!
interface range Gig0/7 - 9
 switchport mode access
 switchport access vlan 30
!
interface Gig0/24
 description Uplink to Router
 switchport mode trunk
!
exit

```






- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)

