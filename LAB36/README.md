<a name="top"></a>
![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB36/image.png)
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

## 🧱 Structured OSPF Network with FastEthernet Links and Metrics

### 1. 🔁 OSPF (Open Shortest Path First)
OSPF is a link-state routing protocol used to find the best path for IP packets based on a shortest-path-first (SPF) algorithm (Dijkstra's algorithm). It's widely used in enterprise networks due to its fast convergence, scalability, and support for hierarchical routing.

- Protocol Type: IGP (Interior Gateway Protocol)
- Metric: Cost (based on bandwidth)
- Routing Type: Link-state
- Convergence Time: Fast

```bash
router ospf 1
 network 172.168.1.0 0.0.0.255 area 0
```
### 2. 🗺️ OSPF Areas
OSPF supports hierarchical design using areas to optimize route processing and improve scalability.

- Area 0: Backbone area – all other areas must connect to this.
- Area 1, 20, 30, 40, etc.: Regular or non-backbone areas.
- ABR (Area Border Router): Connects one or more areas to Area 0.
```shell
interface fa0/0
 ip ospf 1 area 30
```
### 3. 👑 DR and BDR Election
In broadcast or multi-access networks (e.g., Ethernet), OSPF elects a Designated Router (DR) and Backup Designated Router (BDR) to reduce LSA flooding.

- DR: Main router to generate and distribute LSAs.
- BDR: Backup in case the DR fails.
- Election Criteria: Highest OSPF priority or Router ID.
```shell
interface fa0/0
 ip ospf priority 100
```
### 4. ⚙️ OSPF Priority
Used to influence DR/BDR election.

- Range: 0–255 (0 = never DR/BDR)
- Default: 1
- Higher priority wins election

```shell
interface fa0/0
 ip ospf priority 200
``` 
### 6. 💾 Bandwidth Configuration
Bandwidth affects OSPF cost (lower cost = more preferred path).

- Default Cost Formula: Cost = 100,000,000 / Bandwidth (bps)
- Manual Cost Override:
  
```bash
interface fa0/1
 bandwidth 100000
 ip ospf cost 10
```
### 7. 🔐 OSPF Authentication (MD5)
OSPF can use authentication to verify routing updates between neighbors.

- Types: None, Simple Password, or MD5 (recommended)
- MD5 Configuration Example:

```shell
interface fa0/0
 ip ospf message-digest-key 1 md5 Cisco123
 ip ospf authentication message-digest
```
### 8. ⏱️ Hello and Dead Intervals
OSPF routers send Hello packets to discover and maintain neighbor relationships.

- Hello Interval: Time between Hello packets
- Dead Interval: Time before a router is declared down
  
```bash
interface fa0/0
 ip ospf hello-interval 10
 ip ospf dead-interval 40
```
### 9. 🧠 Router ID
A unique 32-bit identifier used to identify the router in OSPF.

- Automatically chosen: Highest IP on loopback, else highest active IP
- Manually configured:

```shell
router ospf 1
 router-id 1.1.1.1
```
### 🔧 Configuration Commands Per Router

```shell
hostname R1
interface Loopback0
 ip address 1.1.1.1 255.255.255.255

interface FastEthernet0/0
 ip address 172.168.1.1 255.255.255.0
 ip ospf priority 100
 ip ospf message-digest-key 1 md5 Cisco123
 ip ospf authentication message-digest
 ip ospf hello-interval 10
 ip ospf dead-interval 40
 no shutdown
```

- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
