<a name="top"></a>
![Timeline2_shutterstoc](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB24/images.png)

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

## 🧪 VLAN Routing Lab – Cisco Packet Tracer (3 Methods)
This lab demonstrates 3 different ways to perform inter-VLAN routing in Cisco networks:

### 🔧 VLAN LAB SCENARIOS OVERVIEW

Lab   | Title                      | Routing Device      | Method
----- | -------------------------- | ------------------- | ---------------------------------------------
1     | Router with Two Interfaces | Router              | Physical Interfaces (fa0/0, fa0/1)
2     | Multilayer Switch Routing  | L3 Switch           | SVIs with ip routing
3     | Router-on-a-Stick          | Router + L2 Switch  | Subinterfaces over trunk

## ✅ LAB 1 – Router with Two Physical Interfaces

### 🖧 Topology:
- Hosts in VLAN 10 and VLAN 20
- Router uses fa0/0 for VLAN 10 and fa0/1 for VLAN 20

### 🔹 Router Configuration (R1):
```bash
Router> enable
Router# configure terminal
!
interface FastEthernet0/0
 ip address 192.168.10.1 255.255.255.0
 no shutdown
!
interface FastEthernet0/1
 ip address 192.168.20.1 255.255.255.0
 no shutdown
!
exit
```

### 🔹 Switch Configuration (SW1):
```bash
Switch> enable
Switch# configure terminal
!
vlan 10
vlan 20
!
interface range FastEthernet0/1 - 3
 switchport mode access
 switchport access vlan 10
!
interface range FastEthernet0/4 - 6
 switchport mode access
 switchport access vlan 20
!
interface FastEthernet0/24
 description Link to Router
 switchport mode access
 switchport access vlan 10
!
interface FastEthernet0/23
 description Link to Router
 switchport mode access
 switchport access vlan 20
!
exit
```
## ✅ LAB 2 – Inter-VLAN Routing Using Multilayer Switch

### 🖧 Topology:
- One multilayer switch (L3SW)
- Hosts in VLAN 10 and VLAN 20
- No external router needed
### 🔹 Multilayer Switch Configuration (L3SW):
``` bash
L3SW> enable
L3SW# configure terminal
!
ip routing
!
vlan 10
vlan 20
!
interface Vlan10
 ip address 192.168.10.1 255.255.255.0
 no shutdown
!
interface Vlan20
 ip address 192.168.20.1 255.255.255.0
 no shutdown
!
interface FastEthernet0/1
 switchport mode access
 switchport access vlan 10
!
interface FastEthernet0/2
 switchport mode access
 switchport access vlan 20
!
exit
```

## ✅ LAB 3 – Router-on-a-Stick (Subinterfaces)
### 🖧 Topology:
- Router + L2 Switch
- Router uses g0/0.10, g0/0.20
- Switch trunk connected to router

### 🔹 Router Configuration (R3):

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
interface GigabitEthernet0/0
 no shutdown
!
exit
```
### 🔹 Switch Configuration (SW3):

```bash
Switch> enable
Switch# configure terminal
!
vlan 10
vlan 20
!
interface range FastEthernet0/1 - 3
 switchport mode access
 switchport access vlan 10
!
interface range FastEthernet0/4 - 6
 switchport mode access
 switchport access vlan 20
!
interface FastEthernet0/24
 description Trunk to Router
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

