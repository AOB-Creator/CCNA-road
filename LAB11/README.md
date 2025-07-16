<a name="top"></a>


![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB11/image.png)

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



## 🧪 Static Routing Between Two Routers with Subnetting Based on Host Requirements
This lab demonstrates static routing between two routers. The network includes subnetting based on the number of hosts in each segment, point-to-point links, and full end-to-end communication using manually configured static routes.

---

## 🧩 Subnet Planning

| Subnet | Description            | Required Hosts | Subnet Mask     | CIDR  | IP Range                 |
|--------|------------------------|----------------|------------------|-------|---------------------------|
| A      | Router1 LAN Network    | 30             | 255.255.255.224  | /27   | 192.168.1.0 – 192.168.1.31 |
| B      | Router1 ↔ Router2 Link | 2              | 255.255.255.252  | /30   | 192.168.2.0 – 192.168.2.3  |
| C      | Router2 LAN Network    | 14             | 255.255.255.240  | /28   | 192.168.3.0 – 192.168.3.15 |

> 🧠 Subnet masks are selected to optimize IP usage based on host requirements.

---

## ⚙️ IP Address Assignment

| Device      | Interface | IP Address      | Subnet |
|-------------|-----------|------------------|--------|
| PC1         | NIC       | 192.168.1.10     | A      |
| Router1     | G0/0      | 192.168.1.1      | A      |
| Router1     | G0/1      | 192.168.2.1      | B      |
| Router2     | G0/0      | 192.168.2.2      | B      |
| Router2     | G0/1      | 192.168.3.1      | C      |
| PC2         | NIC       | 192.168.3.10     | C      |

---

## 📜 Static Routing Configuration

### ▶️ Router 1

```bash
interface G0/0
 ip address 192.168.1.1 255.255.255.224
 no shutdown

interface G0/1
 ip address 192.168.2.1 255.255.255.252
 no shutdown

ip route 192.168.3.0 255.255.255.240 192.168.2.2
```

## ▶️ Router 2
```bash
interface G0/0
 ip address 192.168.2.2 255.255.255.252
 no shutdown

interface G0/1
 ip address 192.168.3.1 255.255.255.240
 no shutdown

ip route 192.168.1.0 255.255.255.224 192.168.2.1

```
## ✅ Verification Commands

### 📡 PC Commands
```bash
# Check IP configuration
ipconfig        # Windows
ifconfig        # Linux/macOS

# Test connectivity
ping [destination IP]
tracert [destination IP]     # Windows
traceroute [destination IP]  # Linux/macOS
```
### 🛠️ Router Commands (Cisco IOS)
```bash
# View routing table
show ip route

# View interface status and IPs
show ip interface brief

# Ping another device from the router
ping [destination IP]

# Trace the route to another device
traceroute [destination IP]

# Check static routes specifically
show running-config | include ip route

# Check if interfaces are up
show interfaces status

```

- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
