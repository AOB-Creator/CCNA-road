<a name="top"></a>
![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB33/image.png)
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

## 🛰️ OSPF Advanced Concepts 

## 📍 Key OSPF Components

| Component | Description |
|----------|-------------|
| **ABR (Area Border Router)** | A router that connects one or more OSPF areas to the backbone (Area 0). Maintains a separate LSDB for each area it connects to. |
| **ASBR (Autonomous System Boundary Router)** | A router that connects the OSPF domain to an external routing domain (e.g., BGP or another OSPF process). Generates Type 5 LSAs. |
| **LSDB (Link-State Database)** | A database that stores all received LSAs for a given area. All routers in an area have identical LSDBs. |
| **SPF (Shortest Path First)** | Dijkstra algorithm used by OSPF to calculate the shortest path to each destination in the LSDB and populate the routing table. |
| **DR (Designated Router)** | Elected router in broadcast and NBMA networks to reduce LSA flooding. Acts as a central point for OSPF updates. |
| **BDR (Backup Designated Router)** | Monitors the DR and takes over its role if the DR fails. Also receives all LSAs but does not forward them. |
| **Transit Area** | An OSPF area that can carry traffic between other OSPF areas (typically Area 0). Allows inter-area communication. |
| **Non-Transit Area** | An area that does not forward traffic between other areas. Examples include stub, totally stubby, and NSSA. |

## 🌐 Transit vs. Non-Transit Areas

| Type                | Description |
|---------------------|-------------|
| **Transit Area**     | A standard OSPF area (usually Area 0) that allows traffic to pass between other OSPF areas. It acts as a central backbone where ABRs exchange inter-area routing information. |
| **Non-Transit Area** | An OSPF area that does not allow traffic to pass between other areas. Used to simplify routing and reduce LSA processing. Includes **Stub**, **Totally Stubby**, and **NSSA (Not-So-Stubby Area)** types. These areas block certain LSA types to limit routing overhead. |


## 🔁 OSPF Routing Flow Example

```mermaid
graph TD
    A[Router in Area 1] -->|Intra-Area LSAs| B[ABR]
    B -->|Type 3 Summary LSAs| C[Area 0 - Backbone]
    C --> D[ABR in Area 2]
    D -->|Type 3 Summary LSAs| E[Router in Area 2]








- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
