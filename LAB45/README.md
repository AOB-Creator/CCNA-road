<a name="top"></a>
![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB43/image.png)
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

## 🧠 Spanning Tree Protocols (STP) – Technical Documentation

Spanning Tree Protocol (STP) is a Layer 2 protocol defined by IEEE 802.1D that prevents loops in Ethernet networks by blocking redundant paths and ensuring a loop-free logical topology.

---

## 📘 Table of Contents
- [What is STP?](#what-is-stp)
- [How STP Works](#how-stp-works)
- [Types of STP Protocols](#types-of-stp-protocols)
- [STP Port States](#stp-port-states)
- [Spanning Tree Path Cost Table](#spanning-tree-path-cost-table)
- [Common STP Configuration Commands (Cisco)](#common-stp-configuration-commands-cisco)
- [Advanced STP Concepts](#advanced-stp-concepts)

---

## 🔍 What is STP?

Spanning Tree Protocol (STP) is designed to:
- **Prevent Layer 2 loops**
- **Provide path redundancy**
- **Elect a Root Bridge** to manage the network tree

---

## 🔁 How STP Works

1. **Root Bridge Election** – Switch with the lowest Bridge ID becomes the Root Bridge.
2. **Path Cost Calculation** – STP calculates the lowest-cost path to the Root Bridge.
3. **Port Roles**:
   - **Root Port (RP)** – Best path to the root
   - **Designated Port (DP)** – Best forwarding port on a segment
   - **Blocked Port** – Backup path to prevent loops

4. **Port State Transitions**:
   - `Blocking → Listening → Learning → Forwarding`

---

## 🌱 Types of STP Protocols

| Protocol         | IEEE Standard | Features                              | Convergence Time | Scalability |
|------------------|----------------|----------------------------------------|------------------|-------------|
| **STP**          | 802.1D         | Original version                       | 30–50 seconds    | Low         |
| **RSTP**         | 802.1w         | Rapid convergence                      | ~6 seconds       | Medium      |
| **MSTP**         | 802.1s         | Multiple VLAN instances                | Moderate         | High        |
| **PVST+**        | Cisco          | Per VLAN STP                           | Medium           | Medium      |
| **RPVST+**       | Cisco          | RSTP per VLAN                          | Fast             | Medium      |
| **BPDU Guard**   | -              | Protects edge ports from rogue BPDUs   | -                | -           |

---

## ⏱ STP Port States

| State       | Description                                   |
|-------------|-----------------------------------------------|
| **Blocking**   | Receives BPDUs only, no data forwarding       |
| **Listening**  | Prepares for STP convergence                  |
| **Learning**   | Learns MAC addresses, no forwarding yet       |
| **Forwarding** | Normal operation, forwarding frames           |
| **Disabled**   | Port is administratively or logically down    |

---

## 📐 Spanning Tree Path Cost Table

| Link Speed | STP Cost |
|------------|----------|
| 10 Mbps    | 100      |
| 100 Mbps   | 19       |
| 1 Gbps     | 4        |
| 10 Gbps    | 2        |

> ℹ️ Lower cost means a more preferred path.

---

## 🛠 Common STP Configuration Commands (Cisco)

```bash
# Set STP priority to influence Root Bridge election
spanning-tree vlan 10 priority 4096

# Set switch as root bridge for VLAN 10
spanning-tree vlan 10 root primary

# Enable Rapid Spanning Tree Protocol
spanning-tree mode rapid-pvst

# Configure PortFast for edge ports (access ports)
interface FastEthernet0/1
 spanning-tree portfast

# Enable BPDU Guard to protect edge ports
 spanning-tree bpduguard enable
```


## 5. STP Variants and Comparison

| Protocol       | IEEE Standard | Vendor      | Characteristics                                        | Convergence Time | VLAN Support    |
|----------------|---------------|-------------|--------------------------------------------------------|------------------|------------------|
| **STP**        | 802.1D        | IEEE        | Classic protocol with long convergence times           | ~30–50 sec       | Single instance  |
| **RSTP**       | 802.1w        | IEEE        | Rapid transitions, faster convergence                  | < 6 sec          | Single instance  |
| **MSTP**       | 802.1s        | IEEE        | Multiple STP instances for VLAN groups (MSTI)          | Moderate         | Multi-VLAN       |
| **PVST+**      | -             | Cisco       | One STP instance per VLAN                              | Medium           | Per VLAN         |
| **Rapid PVST+**| -             | Cisco       | Rapid STP per VLAN                                     | Fast             | Per VLAN         |

> MSTP is ideal for large-scale networks due to instance mapping of VLANs, reducing CPU overhead.



- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
