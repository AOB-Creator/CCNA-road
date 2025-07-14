<a name="top"></a>


![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB20/image.png)

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

## 📡 VLAN Configuration and Trunking Using a Cisco Layer 2 Switch

This lab illustrates a network topology featuring a **central Layer 2 switch (Switch1)** connecting two routers (Router2 and Router3), each linked to multiple PCs organized into **VLANs**. The setup leverages VLANs for logical network segmentation, with appropriate protocols to ensure reliable and efficient communication.

## 🗺️ Topology Description

- **🔌 Switch1**: Cisco 2960-24TT Layer 2 Switch  
  - Connected to Router2 via **Fa0/23**
  - Connected to Router3 via **Fa0/24**

- **🛠 Routers**
  - **Router2**: Interface Fa0/23, IP `192.168.1.3`
  - **Router3**: Interface Fa0/24, IP `192.168.3.3`

- **🌈 VLAN Assignments**
  - **VLAN 10 (Red)** – PCs & Router2
  - **VLAN 20 (Green)** – Subset of PCs under Router2
  - **VLAN 30 (Orange)** – PCs & Router3

---

## 📊 Subnet and IP Details

### 🔴 VLAN 10 – `192.168.1.0/24`
| Device | IP Address     |
|--------|----------------|
| Router2 | 192.168.1.3    |
| PC0     | 192.168.1.2    |
| PC1     | 192.168.1.1    |

- **Range**: 192.168.1.0 – 192.168.1.255  
- **Broadcast**: 192.168.1.255

---

### 🟢 VLAN 20 – `192.168.2.0/24`
| Device | IP Address     |
|--------|----------------|
| PC2     | 192.168.2.2    |
| PC3     | 192.168.2.3    |

- **Range**: 192.168.2.0 – 192.168.2.255  
- **Broadcast**: 192.168.2.255

---

### 🟠 VLAN 30 – `192.168.3.0/24`
| Device | IP Address     |
|--------|----------------|
| Router3 | 192.168.3.3    |
| PC4     | 192.168.3.2    |
| PC5     | 192.168.3.3    |

- **Range**: 192.168.3.0 – 192.168.3.255  
- **Broadcast**: 192.168.3.255

---

## 📡 Protocols Used

| Protocol | Purpose |
|---------|---------|
| **Ethernet** | Layer 2 data transmission between switch and devices |
| **IEEE 802.1Q** | VLAN tagging on trunk links |
| **ARP** | Resolves IP-to-MAC within VLAN |
| **ICMP** | Network diagnostics (e.g., ping) |
| **IPv4** | Addressing with /24 subnet masks |
| **Static Routing / OSPF (optional)** | Inter-VLAN communication on Router2/3 |

---

## 🧰 Technologies

- **VLANs**: Logical segmentation of traffic to reduce broadcast domains
- **Trunking**: Fa0/23 & Fa0/24 carry tagged traffic between routers and switch
- **Access Ports**: Assigned to individual PCs, mapped to specific VLANs
- **Layer 2 Switching**: Operates based on MAC addresses

---

## 🧾 Configuration Examples

### 🔧 Switch1 Configuration

```shell
# Create VLANs
vlan 10
 name RED
vlan 20
 name GREEN
vlan 30
 name ORANGE

# Trunk ports
interface FastEthernet0/23
 switchport mode trunk
 switchport trunk allowed vlan 10,20

interface FastEthernet0/24
 switchport mode trunk
 switchport trunk allowed vlan 30

# Access ports
interface range FastEthernet0/1-4
 switchport mode access
 switchport access vlan 10

interface range FastEthernet0/5-6
 switchport mode access
 switchport access vlan 20

interface range FastEthernet0/7-10
 switchport mode access
 switchport access vlan 30
```




- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
