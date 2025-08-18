<a name="top"></a>
![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB47/image.png)
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



## 🌐 IPv6 and Static Routing Configuration

### 📖 Overview

This guide provides an introduction to IPv6 addressing and how to
configure static routes on Cisco routers and Layer 3 switches. Static
routing is often used in small networks, lab environments, or as a
fallback to dynamic routing protocols.

------------------------------------------------------------------------

## 🔑 IPv6 Basics

-   Address length: 128 bits (hexadecimal format).
-   Notation: 8 groups of 16-bit hexadecimal numbers, separated by
    colons.
    -   Example: 2001:0db8:acad:0001:0000:0000:0000:0001
-   Shortening rules:
    -   Remove leading zeros: 2001:db8:acad:1::1
    -   Use :: once to replace consecutive zeros.

## 📌 IPv6 Address Types

-   Global Unicast (2000::/3) → Public routable addresses.
-   Link-local (FE80::/10) → Required on every interface, not routable
    beyond the link.
-   Unique Local (FC00::/7) → Private IPv6 addressing.
-   Multicast (FF00::/8) → One-to-many communication.
-   Anycast → One-to-nearest communication.

------------------------------------------------------------------------

## ⚙️ IPv6 Interface Configuration

    # Enter interface configuration
    R1(config)# interface gigabitethernet 0/0
    R1(config-if)# ipv6 address 2001:DB8:ACAD:1::1/64
    R1(config-if)# ipv6 enable
    R1(config-if)# no shutdown

Verify with:

    R1# show ipv6 interface brief

------------------------------------------------------------------------

## 🚦 Static Routing in IPv6

1. Directly Connected Static Route

    R1(config)# ipv6 route 2001:DB8:ACAD:2::/64 gigabitethernet 0/1

2. Recursive Static Route (via Next-Hop IPv6 Address)

    R1(config)# ipv6 route 2001:DB8:ACAD:3::/64 2001:DB8:ACAD:2::2

3. Fully Specified Static Route (interface + next-hop)

    R1(config)# ipv6 route 2001:DB8:ACAD:4::/64 gigabitethernet 0/1 2001:DB8:ACAD:2::2

4. Default Static Route (Gateway of Last Resort)

    R1(config)# ipv6 route ::/0 2001:DB8:ACAD:2::2

------------------------------------------------------------------------

## 🔍 Verification Commands

    R1# show ipv6 route
    R1# ping ipv6 2001:DB8:ACAD:3::1
    R1# traceroute ipv6 2001:DB8:ACAD:4::1

------------------------------------------------------------------------

## 📝 Best Practices

-   Always configure link-local addresses automatically (FE80::/10).
-   Use a default static route (::/0) for internet access.
-   Combine static routing with dynamic protocols for redundancy.
-   Document IPv6 addressing plans to avoid overlap.




















- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
