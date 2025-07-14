<a name="top"></a>


![Timeline2_shutterstoc](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB23/image.png)

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

## 📡 Interconnected VLANs over Bus Topology with VTP and Multilayer Switches

This lab demonstrates a network topology with a bus architecture, utilizing four multilayer switches (LS2, LS3, LS4, LS5), each integrating internal Layer 2 switches. The network is segmented into multiple VLANs to support different departments and roles, connected via a central VTP (VLAN Trunking Protocol) server and VTP transparent switch.

## Topology
- **Multilayer Switches**:
  - **LS2**: Connected to VTP Server via Fa0/23 and Switch2 via Fa0/24.
  - **LS3**: Connected to VTP Server via Fa0/23 and Switch3 via Fa0/24.
  - **LS4**: Connected to VTP Transparent via Fa0/23 and Switch4 via Fa0/24.
  - **LS5**: Connected to VTP Transparent via Fa0/23 and Switch5 via Fa0/24.
- **Central Devices**:
  - **VTP Server**: Manages VLAN configurations, connected to LS2, LS3, LS4, and LS5 via Gig0/1.
  - **VTP Transparent**: Facilitates VLAN propagation, connected to LS4 and LS5 via Gig0/2.
- **Bus Topology**: Switches are interconnected in a linear bus configuration using trunk links.

## VLAN Configuration
- **VLAN 10 - Sales (Green)**: 192.168.10.0/24
- **VLAN 20 - CEO (Blue)**: 192.168.20.0/24
- **VLAN 30 - R&D (Orange)**: 192.168.30.0/24
- **VLAN 40 - NASA (Black)**: 192.168.40.0/24
- **VLAN 50 - NATO (Purple)**: 192.168.50.0/24

## Subnet and IP Details
- **VLAN 10 (Sales)**:
  - LS2: 192.168.10.2
  - PCs: PC7 (192.168.10.3), PC13 (192.168.10.5)
- **VLAN 20 (CEO)**:
  - LS3: 192.168.20.4
  - PCs: PC0 (192.168.20.5), PC1 (192.168.20.2)
- **VLAN 30 (R&D)**:
  - LS4: 192.168.30.2
  - PCs: PC2 (192.168.30.3), PC3 (192.168.30.4)
- **VLAN 40 (NASA)**:
  - LS5: 192.168.40.5
  - PCs: PC4 (192.168.40.2), PC5 (192.168.40.3)
- **VLAN 50 (NATO)**:
  - LS5: 192.168.50.4
  - PCs: PC6 (192.168.50.2), PC11 (192.168.50.3)

## Protocols
- **Ethernet**: Layer 2 communication over FastEthernet and GigabitEthernet.
- **IEEE 802.1Q**: VLAN tagging for trunk links.
- **VTP (VLAN Trunking Protocol)**: Centralized VLAN management.
- **ARP**: Resolves IP to MAC addresses.
- **ICMP**: Ping for testing connectivity.
- **IP (IPv4)**: Subnetting with /24 masks.
- **STP**: Loop prevention in bus topology.

## Technologies
- **Multilayer Switching**: Switching and routing on LS2–LS5.
- **VLANs**: Isolated broadcast domains for departments.
- **Trunking**: Inter-switch VLAN communication.
- **Bus Topology**: Centralized and efficient design.

## Configuration

### VTP Server
```bash
vtp mode server
vtp domain LAB
vlan 10
 name Sales
vlan 20
 name CEO
vlan 30
 name R&D
vlan 40
 name NASA
vlan 50
 name NATO
interface GigabitEthernet0/1
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30,40,50
```
## L2 Switches
```bash
vtp mode client
vtp domain LAB
interface FastEthernet0/23
 switchport mode trunk
 switchport trunk allowed vlan 10
interface FastEthernet0/24
 switchport mode trunk
 switchport trunk allowed vlan 10
interface Vlan10
 ip address 192.168.10.2 255.255.255.0
 no shutdown
ip default-gateway 192.168.10.1
```
## ✅ Verification Commands

### 🔧 On VTP Server and Transparent Switch
- `show vtp status`  
  _Displays the current VTP mode, domain name, configuration revision number, and VLANs learned or created._
- `show vlan brief`  
  _Lists all VLANs and the ports assigned to each VLAN._
- `show interfaces trunk`  
  _Shows trunk interfaces and which VLANs are allowed or active._

### 🖧 On Multilayer Switches (LS2, LS3, LS4, LS5)
- `show ip interface brief`  
  _Displays the status and IP addresses of all interfaces._
- `show vlan brief`  
  _Confirms correct VLAN-to-port assignments._
- `show interfaces trunk`  
  _Verifies trunk links and allowed VLANs on Fa0/23 and Fa0/24._
- `ping [IP Address]`  
  _Used to test connectivity to other devices within or across VLANs._
- `show spanning-tree`  
  _Checks if Spanning Tree Protocol is running and which ports are blocked or forwarding._

### 🖥️ On PCs
- `ping [gateway IP]`  
  _Verifies basic connectivity to the default gateway (multilayer switch)._
- `ping [other PC IP]`  
  _Tests intra-VLAN or inter-VLAN communication._
- `ipconfig` (on Windows) / `ifconfig` (on Linux)  
  _Displays IP configuration of the PC for troubleshooting._

---

📝 **Note**: If inter-VLAN routing is not working, verify:
- VLAN interfaces are up (`no shutdown`)
- IPs are correctly assigned
- Trunk links are passing the correct VLANs
- Devices are using the correct gateways




- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)

