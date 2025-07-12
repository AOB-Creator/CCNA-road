<a name="top"></a>
![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB35/image.png)
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

## 📡 Advanced Routing and Switching: Multi-Area OSPF with Inter-VLAN Communication

Multi-area OSPF setup with multiple VLANs across three major areas (10, 20, 30) being routed through Area 0 (VLAN 77). Below is a breakdown of your configuration and how to ensure it works:

# 🌐 Multi-Area OSPF Routing with VLAN Segmentation

This project demonstrates a scalable enterprise network using **Multi-Area OSPF (Open Shortest Path First)** routing with **multiple VLANs** across different areas. All inter-area routing is handled through **VLAN 77 (Area 0)** acting as the backbone.

---

## 🗺️ Network Overview

- 🔁 **OSPF Dynamic Routing Protocol**
- 🧩 **VLAN Segmentation** for traffic isolation
- 🔄 **Multi-Area OSPF Topology**
- 🌉 VLAN 77 serves as the **Backbone Area (Area 0)**
- 🧪 Simulated in **Cisco Packet Tracer**

---

## 🔁 OSPF Areas Table

| **Area ID** | **Connected VLANs**                   | **Routers Involved**       | **Purpose / Role**                       |
|-------------|----------------------------------------|-----------------------------|-------------------------------------------|
| `Area 0`    | VLAN 77 (Backbone)                    | R1, R2, R4                  | Backbone area, interconnects all other areas |
| `Area 10`   | VLAN 50, 60, 70, 80                   | R0, R1                      | End-user access network, routed through R1 |
| `Area 20`   | VLAN 10, 20, 70, 80                   | R2, R3                      | Separate user segment routed via R2        |
| `Area 30`   | VLAN 10, 20, 70                       | R4, R5                      | Access area, traffic routed through R4     |

---

## 🧱 VLAN Configuration

| **VLAN ID** | **IP Subnet**       | **Devices**              |
|------------|----------------------|---------------------------|
| VLAN 10    | `192.168.10.0/24`   | PC4, PC11                |
| VLAN 20    | `192.168.20.0/24`   | PC5, PC10                |
| VLAN 50    | `192.168.50.0/24`   | PC0, PC1, PC8            |
| VLAN 60    | `192.168.60.0/24`   | PC2                      |
| VLAN 70    | `192.168.70.0/24`   | PC3, PC6, PC9, PC10, PC11 |
| VLAN 80    | `192.168.80.0/24`   | PC0, PC7                 |
| VLAN 77    | `10.10.10.0/29`     | Transit (Backbone)       |

---

## ⚙️ Routing Setup Summary

- **OSPF Process ID**: `1` on all routers
- **ABRs (Area Border Routers)**:
  - R1: Area 10 ↔ Area 0
  - R2: Area 20 ↔ Area 0
  - R4: Area 30 ↔ Area 0
- **Inter-area communication** happens through **VLAN 77 (Backbone)**

---

## 🧪 Testing & Verification

- 🔁 `ping` between hosts in different areas
- 📶 `show ip ospf neighbor` on routers to verify adjacencies
- 🧾 `show ip route` to view OSPF-learned routes

---

## 🛠️ Tools Used

- 🧪 Cisco Packet Tracer 8.x
- 📡 Cisco 2811 Routers
- 🔀 Cisco 2960 Switches
- 💬 CLI Configuration

## 🛠️ OSPF Configuration Plan
We’ll configure each router with:

- Loopback as Router ID
- Interfaces in their respective OSPF areas
- Backbone (Area 0) as required for inter-area communication

```bash
# 🔧 Router 0 (R0) - Area 10
hostname R0
interface Gig0/0
 ip address 192.168.50.1 255.255.255.0
interface Gig0/1
 ip address 192.168.60.1 255.255.255.0
interface Gig0/2
 ip address 192.168.70.1 255.255.255.0
interface Gig0/3
 ip address 192.168.80.1 255.255.255.0
router ospf 1
 router-id 1.1.1.1
 network 192.168.50.0 0.0.0.255 area 10
 network 192.168.60.0 0.0.0.255 area 10
 network 192.168.70.0 0.0.0.255 area 10
 network 192.168.80.0 0.0.0.255 area 10

# 🔧 Router 1 (R1) - ABR Area 10 <-> 0
hostname R1
interface Gig0/0
 ip address 192.168.70.2 255.255.255.0
interface Gig0/1
 ip address 10.10.10.1 255.255.255.248
router ospf 1
 router-id 2.2.2.2
 network 192.168.70.0 0.0.0.255 area 10
 network 10.10.10.0 0.0.0.7 area 0

# 🔧 Router 2 (R2) - ABR Area 20 <-> 0
hostname R2
interface Gig0/0
 ip address 192.168.10.1 255.255.255.0
interface Gig0/1
 ip address 192.168.20.1 255.255.255.0
interface Gig0/2
 ip address 10.10.10.2 255.255.255.248
router ospf 1
 router-id 5.5.5.5
 network 192.168.10.0 0.0.0.255 area 20
 network 192.168.20.0 0.0.0.255 area 20
 network 10.10.10.0 0.0.0.7 area 0

# 🔧 Router 3 (R3) - Area 20
hostname R3
interface Gig0/0
 ip address 192.168.20.2 255.255.255.0
interface Gig0/1
 ip address 192.168.80.2 255.255.255.0
router ospf 1
 router-id 6.6.6.6
 network 192.168.20.0 0.0.0.255 area 20
 network 192.168.80.0 0.0.0.255 area 20

# 🔧 Router 4 (R4) - ABR Area 30 <-> 0
hostname R4
interface Gig0/0
 ip address 192.168.10.2 255.255.255.0
interface Gig0/1
 ip address 192.168.70.3 255.255.255.0
interface Gig0/2
 ip address 10.10.10.3 255.255.255.248
router ospf 1
 router-id 3.3.3.3
 network 192.168.10.0 0.0.0.255 area 30
 network 192.168.70.0 0.0.0.255 area 30
 network 10.10.10.0 0.0.0.7 area 0

# 🔧 Router 5 (R5) - Area 30
hostname R5
interface Gig0/0
 ip address 192.168.10.3 255.255.255.0
interface Gig0/1
 ip address 192.168.20.3 255.255.255.0
interface Gig0/2
 ip address 192.168.70.4 255.255.255.0
router ospf 1
 router-id 4.4.4.4
 network 192.168.10.0 0.0.0.255 area 30
 network 192.168.20.0 0.0.0.255 area 30
 network 192.168.70.0 0.0.0.255 area 30

# 🔧 Switches
# You can configure VLANs and trunk ports as needed
# Example:
vlan 10
vlan 20
vlan 50
vlan 60
vlan 70
vlan 77
vlan 80

interface range fa0/1 - 24
 switchport mode access
 switchport access vlan [X]  # Replace X with correct VLAN

interface Gig0/1
 switchport trunk encapsulation dot1q
 switchport mode trunk

```



---

## 📌 Author

🧑‍💻 **Alpamis Omirbekov**  
💼 Multi-area OSPF Network Design – Lab Exercise  
📍 Nukus, Uzbekistan  


























- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
