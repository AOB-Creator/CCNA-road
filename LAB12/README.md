<a name="top"></a>


![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB12/image.png)

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

## 🚌 Static Routing Lab with 7 Routers in a Bus Topology

This lab represents a network topology with multiple routers, switches, and PCs configured across different subnets. The setup includes a **linear (bus) arrangement** of 7 routers connected via `Fa0/0` and `Fa0/1` interfaces, each branching out to a switch with multiple PCs. Static routing is manually configured between each router to ensure end-to-end communication.

---

## 🧩 Subnet Tables

### 🌐 Subnet 1: 192.168.1.0/27

| Device     | Interface | IP Address     |
|------------|-----------|----------------|
| Router0    | Fa0/0     | 192.168.1.1    |
| PC1        | Fa0       | 192.168.1.2    |
| PC2        | Fa0       | 192.168.1.3    |
| PC3        | Fa0       | 192.168.1.4    |
| PC4        | Fa0       | 192.168.1.5    |
| PC5        | Fa0       | 192.168.1.6    |
| PC6        | Fa0       | 192.168.1.7    |

> 🗂 Range: 192.168.1.0 - 192.168.1.31 | Broadcast: 192.168.1.31

---

### 🌐 Subnet 2: 192.168.2.0/27

| Device     | Interface | IP Address     |
|------------|-----------|----------------|
| Router1    | Fa0/0     | 192.168.2.1    |
| PC1        | Fa0       | 192.168.2.2    |
| PC2        | Fa0       | 192.168.2.3    |
| PC3        | Fa0       | 192.168.2.4    |
| PC4        | Fa0       | 192.168.2.5    |
| PC5        | Fa0       | 192.168.2.6    |
| PC6        | Fa0       | 192.168.2.7    |

> 🗂 Range: 192.168.2.0 - 192.168.2.31 | Broadcast: 192.168.2.31

---

### 🌐 Subnet 3: 192.168.3.0/27

| Device     | Interface | IP Address     |
|------------|-----------|----------------|
| Router2    | Fa0/0     | 192.168.3.1    |
| PC1        | Fa0       | 192.168.3.2    |
| PC2        | Fa0       | 192.168.3.3    |
| PC3        | Fa0       | 192.168.3.4    |
| PC4        | Fa0       | 192.168.3.5    |
| PC5        | Fa0       | 192.168.3.6    |
| PC6        | Fa0       | 192.168.3.7    |

> 🗂 Range: 192.168.3.0 - 192.168.3.31 | Broadcast: 192.168.3.31

---

### 🌐 Subnet 4: 192.168.4.0/27

| Device     | Interface | IP Address     |
|------------|-----------|----------------|
| Router3    | Fa0/0     | 192.168.4.1    |
| PC1        | Fa0       | 192.168.4.2    |
| PC2        | Fa0       | 192.168.4.3    |
| PC3        | Fa0       | 192.168.4.4    |
| PC4        | Fa0       | 192.168.4.5    |
| PC5        | Fa0       | 192.168.4.6    |
| PC6        | Fa0       | 192.168.4.7    |

> 🗂 Range: 192.168.4.0 - 192.168.4.31 | Broadcast: 192.168.4.31

---

### 🌐 Subnet 5: 192.168.5.0/27

| Device     | Interface | IP Address     |
|------------|-----------|----------------|
| Router4    | Fa0/0     | 192.168.5.1    |
| PC1        | Fa0       | 192.168.5.2    |
| PC2        | Fa0       | 192.168.5.3    |
| PC3        | Fa0       | 192.168.5.4    |
| PC4        | Fa0       | 192.168.5.5    |
| PC5        | Fa0       | 192.168.5.6    |
| PC6        | Fa0       | 192.168.5.7    |

> 🗂 Range: 192.168.5.0 - 192.168.5.31 | Broadcast: 192.168.5.31

---

### 🌐 Subnet 6: 192.168.6.0/27

| Device     | Interface | IP Address     |
|------------|-----------|----------------|
| Router5    | Fa0/0     | 192.168.6.1    |
| PC1        | Fa0       | 192.168.6.2    |
| PC2        | Fa0       | 192.168.6.3    |
| PC3        | Fa0       | 192.168.6.4    |
| PC4        | Fa0       | 192.168.6.5    |
| PC5        | Fa0       | 192.168.6.6    |
| PC6        | Fa0       | 192.168.6.7    |

> 🗂 Range: 192.168.6.0 - 192.168.6.31 | Broadcast: 192.168.6.31

---

### 🌐 Subnet 7: 192.168.7.0/27

| Device     | Interface | IP Address     |
|------------|-----------|----------------|
| Router6    | Fa0/0     | 192.168.7.1    |
| PC1        | Fa0       | 192.168.7.2    |
| PC2        | Fa0       | 192.168.7.3    |
| PC3        | Fa0       | 192.168.7.4    |
| PC4        | Fa0       | 192.168.7.5    |
| PC5        | Fa0       | 192.168.7.6    |
| PC6        | Fa0       | 192.168.7.7    |

> 🗂 Range: 192.168.7.0 - 192.168.7.31 | Broadcast: 192.168.7.31

---

## 🗺️ Topology Summary

Each router is connected in a linear chain via `Fa0/1` ↔ `Fa0/1` interfaces for inter-router connections. Local devices are connected through switches via `Fa0/0`.

```text
[PCs]--[Switch0]--Router0--Router1--Router2--Router3--Router4--Router5--Router6--[Switch6]--[PCs]


## Topology
- **Routers**: Connected in a linear chain (Router0 to Router6) via Fa0/0 interfaces.
- **Switches**: Each router connects to a switch (Switch0 to Switch6) via GigabitEthernet (Gig0/1) interfaces.
- **PCs**: Six PCs per switch, connected via Fa0/1 to Fa0/6 interfaces.
- **IP Addressing**: Each subnet uses a /27 mask, providing 32 IP addresses per subnet (30 usable host addresses).

## Notes
- Ensure proper routing configuration (e.g., static routes or a routing protocol) between routers for inter-subnet communication.
- Verify switch VLAN configurations to match the subnet assignments.
- All IP addresses are assigned based on the diagram provided.


- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
