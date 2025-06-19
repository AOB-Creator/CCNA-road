<a name="top"></a>

![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAN19/image.png)

[![OS](https://img.shields.io/badge/OS-linux%2C%20windows%2C%20macOS-0078D4)]()
[![CPU](https://img.shields.io/badge/CPU-x86%2C%20x64%2C%20ARM%2C%20ARM64-FF8C00)]()
[![security rating](https://sonarcloud.io/api/project_badges/measure?project=Abblix_Oidc.Server&metric=security_rating)]()
[![reliability rating](https://sonarcloud.io/api/project_badges/measure?project=Abblix_Oidc.Server&metric=reliability_rating)]()
[![maintainability rating](https://sonarcloud.io/api/project_badges/measure?project=Abblix_Oidc.Server&metric=sqale_rating)](
[![getting started](https://img.shields.io/badge/getting_started-guide-1D76DB)]()
[![Free](https://img.shields.io/badge/free_for_non_commercial_use-brightgreen)](#-license)

⭐ Star us on GitHub — it motivates us a lot!

[![Share](https://img.shields.io/badge/share-000000?logo=x&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-1877F2?logo=facebook&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-0A66C2?logo=linkedin&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-FF4500?logo=reddit&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-0088CC?logo=telegram&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)

# 🛠️ Multilayer Switch Configuration Guide

This project outlines the step-by-step configuration of a **Multilayer Switch** for inter-VLAN routing, Layer 3 functionalities, and static/dynamic routing using Cisco IOS.

---

## 📌 Project Overview

Multilayer switches combine Layer 2 switching and Layer 3 routing, enabling efficient inter-VLAN routing and high-speed packet forwarding. This guide includes:

- VLAN creation
- SVIs (Switch Virtual Interfaces)
- Static routing between VLANs
- Routing protocol configuration (optional)

---

## 🧰 Network Topology Example

- Switch Model: Cisco Catalyst 3750
- VLANs: 101 (Staff), 102 (Admin), 103 (Guest)
- Ports: Fa0/1–Fa0/24
- Routed Ports: Gi1/1, Gi1/2

---

## 🔧 Configuration Steps

## 1. **Create VLANs**

```bash
Switch(config)# vlan 101
Switch(config-vlan)# name Staff
Switch(config)# vlan 102
Switch(config-vlan)# name Admin
Switch(config)# vlan 103
Switch(config-vlan)# name Guest
```
##2. Assign Ports to VLANs


```bash

Switch(config)# interface range fa0/1 - 10
Switch(config-if-range)# switchport mode access
Switch(config-if-range)# switchport access vlan 101

```

##3. Create SVIs (Switch Virtual Interfaces)

```bash
Switch(config)# interface vlan 101
Switch(config-if)# ip address 192.168.101.1 255.255.255.0
Switch(config)# interface vlan 102
Switch(config-if)# ip address 192.168.102.1 255.255.255.0
Switch(config)# interface vlan 103
Switch(config-if)# ip address 192.168.103.1 255.255.255.0
```

##Enable routing

```bash 
Switch(config)# ip routing
```
##4. Configure Routed Ports (If used as router ports)

```bash 
Switch(config)# interface gi1/1
Switch(config-if)# no switchport
Switch(config-if)# ip address 10.0.0.1 255.255.255.0
Switch(config-if)# no shutdown
```

# 🌐 Multilayer Switch Network with DNS and HTTPS Servers

This guide includes configuring a Multilayer Switch along with **DNS** and **HTTPS** servers in a Layer 3 environment.

---

## 🖥️ Servers in the Network

| Server Type | IP Address       | VLAN | Purpose              |
|-------------|------------------|------|----------------------|
| DNS Server  | 192.168.50.10    | 50   | Resolving hostnames  |
| HTTPS Server| 192.168.60.10    | 60   | Secure web access    |

---

## 🔧 Server VLAN & SVI Setup

### 1. **Create VLANs and Assign IPs to SVIs**

```bash
Switch(config)# vlan 50
Switch(config-vlan)# name DNS_VLAN
Switch(config)# vlan 60
Switch(config-vlan)# name HTTPS_VLAN

Switch(config)# interface vlan 50
Switch(config-if)# ip address 192.168.50.1 255.255.255.0
Switch(config)# interface vlan 60
Switch(config-if)# ip address 192.168.60.1 255.255.255.0
Switch(config)# ip routing
```







- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
