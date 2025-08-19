<a name="top"></a>
![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB48/image.png)
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



## 🌐 IPv6 + OSPFv3 Configurations

## Step 1: Enable IPv6 Routing
On **every router**:
```bash
R(config)# ipv6 unicast-routing
```

---

## Step 2: Assign IPv6 Addresses

### Example Topology
- **R1 ↔ R2 link** → `fd00:12::/64`
- **R1 LAN** → `fd00:1::/64`
- **R2 LAN** → `fd00:2::/64`

### R1
```bash
R1(config)# interface g0/0
R1(config-if)# ipv6 address fd00:1::1/64
R1(config-if)# ipv6 ospf 10 area 0
no shutdown

R1(config)# interface g0/1
R1(config-if)# ipv6 address fd00:12::1/64
R1(config-if)# ipv6 ospf 10 area 0
no shutdown
```

### R2
```bash
R2(config)# interface g0/0
R2(config-if)# ipv6 address fd00:2::1/64
R2(config-if)# ipv6 ospf 10 area 0
no shutdown

R2(config)# interface g0/1
R2(config-if)# ipv6 address fd00:12::2/64
R2(config-if)# ipv6 ospf 10 area 0
no shutdown
```

---

## Step 3: Enable OSPFv3 Process
OSPFv3 requires a **router ID** (IPv4-style, 32-bit).

### R1
```bash
R1(config)# ipv6 router ospf 10
R1(config-rtr)# router-id 1.1.1.1
```

### R2
```bash
R2(config)# ipv6 router ospf 10
R2(config-rtr)# router-id 2.2.2.2
```

---

## Step 4: Verify
Check neighbors:
```bash
show ipv6 ospf neighbor
```

Check learned routes:
```bash
show ipv6 route ospf
```

Test connectivity:
```bash
ping fd00:2::10    ! from a host in R1 LAN to host in R2 LAN
```

---

## Step 5: Host Configuration (Packet Tracer PCs)
- **PC1 in R1 LAN**
  - IPv6: `fd00:1::10/64`
  - Gateway: `fd00:1::1`
- **PC2 in R2 LAN**
  - IPv6: `fd00:2::10/64`
  - Gateway: `fd00:2::1`

Now both PCs can ping each other via OSPFv3-learned routes. ✅  

---

⚡ Bonus: You can extend this to multiple routers — just keep assigning unique `/64` subnets and enable `ipv6 ospf <pid> area 0` on each interface.



- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
