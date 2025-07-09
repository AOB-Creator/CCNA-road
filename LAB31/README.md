<a name="top"></a>


![Timeline2_shutterstoc](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB31/image.png)

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

## 🌐 RIP (Routing Information Protocol) – Overview

RIP is one of the oldest dynamic distance-vector routing protocols used to help routers exchange routing information within an IP network.

---

## 📌 Key Features of RIP

| Feature                   | Description                                                                 |
|---------------------------|-----------------------------------------------------------------------------|
| **Protocol Type**         | Distance-vector                                                             |
| **Routing Algorithm**     | Bellman-Ford                                                                |
| **Metric Used**           | Hop Count                                                                   |
| **Maximum Hop Count**     | 15 (16 is considered unreachable)                                           |
| **Routing Updates**       | Sent every 30 seconds                                                       |
| **Convergence**           | Slow (compared to modern protocols)                                         |
| **Administrative Distance** | 120                                                                       |
| **Protocol Versions**     | RIPv1 (classful), RIPv2 (classless)                                         |
| **Transport Protocol**    | UDP                                                                         |
| **UDP Port Number**       | 520                                                                         |
| **Update Method**         | RIPv1: Broadcast (255.255.255.255), RIPv2: Multicast (224.0.0.9)            |
| **Authentication**        | Supported in RIPv2 (Plaintext or MD5)                                       |
| **VLSM Support**          | Not supported in RIPv1, supported in RIPv2                                  |
| **Auto Summarization**    | Enabled by default; can be disabled with `no auto-summary` (in RIPv2)      |
| **Suitable for**          | Small to medium-sized networks                                              |



## 🔁 How RIP Works

- Router Initialization: Routers send their routing tables to directly connected neighbors.
- Routing Update: Every 30 seconds, routers broadcast their full routing tables.
- Routing Table Update: If a route with a better metric (fewer hops) is received, the table is updated.
- Invalid Timer: If no updates are received for 180 seconds, the route is marked invalid.
- Hold-down & Flush Timers: These manage route invalidation and removal.

## 🧠 RIP Versions

| Feature                   | RIPv1                                | RIPv2                                  |
|---------------------------|--------------------------------------|----------------------------------------|
| **Routing Type**          | Classful                             | Classless                              |
| **Subnet Mask Support**   | ❌ No                                | ✅ Yes                                 |
| **VLSM Support**          | ❌ No                                | ✅ Yes                                 |
| **Update Method**         | Broadcast (255.255.255.255)          | Multicast (224.0.0.9)                  |
| **Authentication**        | ❌ Not supported                     | ✅ Supported (Plaintext or MD5)        |
| **Route Tagging**         | ❌ No                                | ✅ Yes                                 |
| **Backward Compatibility**| ✅ Compatible with older systems     | ✅ Compatible with RIPv1                |
| **Introduced In**         | 1988                                 | 1994                                   |


## 🧰 RIP Configuration (Cisco IOS Example)

### 🏗️ Basic RIP Configuration
```bash
Router> enable
Router# configure terminal
Router(config)# router rip
Router(config-router)# version 2
Router(config-router)# no auto-summary
Router(config-router)# network 192.168.1.0
Router(config-router)# network 10.0.0.0


## 🔎 Verify RIP Configuration
```bash
Router# show ip protocols
Router# show ip route rip
Router# debug ip rip
```
## ✅ RIP Configuration Summary

| Command                       | Description                                                         |
|------------------------------|---------------------------------------------------------------------|
| `router rip`                 | Enter RIP routing configuration mode                                |
| `version 2`                  | Enable RIP version 2                                                |
| `no auto-summary`            | Disable automatic classful summarization                            |
| `network [network-address]` | Advertise a network in RIP                                          |
| `interface loopback0`        | Create a virtual loopback interface                                 |
| `ip address [ip] [mask]`     | Assign IP address to interface                                      |
| `show ip protocols`          | Display routing protocol information                                |
| `show ip route rip`          | Show routes learned via RIP                                         |
| `debug ip rip`               | Enable RIP packet-level debugging                                   |
| `passive-interface [if]`     | Prevent sending RIP updates out of the specified interface          |
| `clear ip route *`           | Clear the IP routing table                                          |


- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)

