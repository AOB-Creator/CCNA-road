<a name="top"></a>

![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB21/image.png)

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

## 🌐 VLANs Explained: Logical Grouping Beyond Physical Boundaries
A VLAN is a virtual subgroup of devices within a LAN (Local Area Network) that are grouped together based on function, department, or application, not on physical location. Devices in the same VLAN can communicate as if they were on the same physical network, even if they are physically far apart.

## 🔹 Why Use VLANs?

Multilayer switches combine Layer 2 switching and Layer 3 routing, enabling efficient inter-VLAN routing and high-speed packet forwarding. This guide includes:

- Segmentation – Divide a large network into smaller parts.
- Security – Restrict broadcast domains and isolate sensitive departments (e.g., HR from IT).
- Performance – Reduces unnecessary traffic by limiting broadcast domains.
- Manageability – Easier to manage users and policies.
- Flexibility – Logical grouping of users regardless of location.

---

## 🔹 VLAN Types

| VLAN Type         | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| **Default VLAN**   | All switch ports belong to this VLAN by default (usually VLAN 1).           |
| **Data VLAN**      | Used to carry user-generated traffic (excluding voice, management, etc.).   |
| **Voice VLAN**     | Dedicated VLAN for Voice over IP (VoIP) traffic with high priority.         |
| **Management VLAN**| Used for managing network devices via protocols like SSH, Telnet, SNMP.     |
| **Native VLAN**    | Handles untagged traffic on trunk ports (default is VLAN 1).                |
| **Trunk VLAN**     | VLANs allowed to pass over a trunk link between switches.                   |
| **Private VLAN**   | Isolates ports within a VLAN to increase security and control.              |
| **Static VLAN**    | VLAN manually assigned to specific ports by a network admin.                |
| **Dynamic VLAN**   | VLAN assigned automatically based on device MAC address via VMPS.           |


##🔹 How VLAN Works (Simplified):
- A switch port is assigned to a specific VLAN.
- Devices connected to that port are automatically part of that VLAN.
- VLAN-tagged traffic uses IEEE 802.1Q standard.
- A trunk port allows multiple VLANs on a single physical link between switches.
- Router-on-a-Stick or Layer 3 Switch is used for inter-VLAN routing.

## 🔹 Key VLAN Commands (Cisco IOS Example):

```bash
# Create VLAN
Switch(config)# vlan 10
Switch(config-vlan)# name HR

# Assign VLAN to port
Switch(config)# interface fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10

# Configure trunk port
Switch(config)# interface fa0/24
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 10,20,30
```

## 🔧 VLAN Database and Trunk Port Configuration (Cisco IOS)

### 🗂️ VLAN Database Configuration

Use these commands to create VLANs and name them:

```bash
Switch# configure terminal
Switch(config)# vlan 10
Switch(config-vlan)# name HR
Switch(config-vlan)# exit

Switch(config)# vlan 20
Switch(config-vlan)# name SALES
Switch(config-vlan)# exit

Switch(config)# interface fa0/24
Switch(config-if)# switchport trunk allowed vlan add 10

Switch(config-if)# switchport trunk allowed vlan remove 10

```

### 📋 Verify Configuration

After configuring VLANs and trunk ports, use the following commands to verify everything is working correctly.

#### 🔍 Show VLAN Information

```bash
Switch# show vlan brief
Switch# show interfaces trunk
Switch# show interfaces switchport
Switch# show running-config
```

- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
