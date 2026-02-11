<a name="top"></a>


![Timeline2_shutterstoc](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB29/image.png)

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

# 📌 Route Summarization & CIDR Aggregation

At this point, we know what the routing function is all about. Routers will maintain intelligence of the network topology and forward packets based on destinations, selecting the best path across that topology. That intelligence of the topology and changes in the topology are maintained statically or dynamically.

---

## 🔹 Identifying Static and Dynamic Routes

Static routes do not add overhead in the form of routing protocols, advertisements, and extra intelligence on the routers. They are fairly simple to configure and if you remain within a certain limit in terms of the number of static routes, then they are very flexible. However, they are static and so the router will not adjust to network changes, if you use static routing.
  
---
## 🔹 Static Routes
It is on those scenarios of stub networks like the one in the figure with a single link into the rest of the network, that static routing is a suitable answer.

![Timeline2_shutterstoc](https://www.learncisco.net/wp-content/themes/learncisco/assets/images/icnd1/90-static-routing.jpg)

## 🔹 1. Standard Static Route

 - Description: A manually configured route that defines a specific destination network and next-hop IP address or exit interface.
 - Use case: Used for basic routing between networks.
 - Command example:


```bash
  ip route 192.168.2.0 255.255.255.0 192.168.1.2
```
## 🔹 2. Default Static Route

 - Description: A catch-all route used when no other specific route matches the destination IP address.
 - Use case: Typically used to route traffic to the internet or a next-hop router when the destination is unknown.

```bash
  ip route 192.168.2.0 255.255.255.0 192.168.1.2 100
```
## 🔹 3. Floating Static Route

- Description: A backup route with a higher administrative distance than the primary route.
- Use case: Used for redundancy or failover in case the primary route becomes unavailable.


```bash
  ip route 192.168.2.0 255.255.255.0 192.168.1.2
```

## 🔹 (Bonus) Summary Static Route

- Description: A single static route that summarizes multiple networks into one.
- Use case: Reduces the size of routing tables.


```bash
  ip route 192.168.0.0 255.255.252.0 192.168.1.1
```

To calculate a summary static route, you need to find a single route that can represent multiple contiguous subnets. Here's a step-by-step guide to calculate it manually:

### ✅ Steps to Calculate a Summary Static Route

▶️ Example Subnets:

Let’s say you want to summarize these four routes:

  -   192.168.4.0/24
  -   192.168.5.0/24
  -   192.168.6.0/24
  -   192.168.7.0/24

## ① Convert IPs to Binary

### ① Convert IPs to Binary

| Subnet         | Binary Representation                                |
|----------------|-------------------------------------------------------|
| 192.168.4.0    | 11000000.10101000.00000100.00000000                  |
| 192.168.5.0    | 11000000.10101000.00000101.00000000                  |
| 192.168.6.0    | 11000000.10101000.00000110.00000000                  |
| 192.168.7.0    | 11000000.10101000.00000111.00000000                  |


##  Find Matching Bits (Leftmost Common Prefix)

```bash
192.168.4.0  -> 00000100
192.168.5.0  -> 00000101
192.168.6.0  -> 00000110
192.168.7.0  -> 00000111
```
## Determine the Summary Mask

    192.168.4.0 = 11000000.10101000.00000100.00000000
    Common bits: 22 → So the summary subnet mask is /22.


- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)

