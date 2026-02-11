<a name="top"></a>


![Timeline2_shutterstoc](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB28/image.png)

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

Summary routing (also called route summarization or supernetting) is the process of combining multiple IP routes into a single summarized (aggregate) route. It's used in large networks to simplify routing tables and improve efficiency.

## 🚦 Reducing Routing Table with /22 Summary

   - Reduces size of routing tables
   - Speeds up routing lookups
   - Minimizes bandwidth usage for routing updates
   - Provides better route stability

## 🧠 How It Works
Summary routing creates one route that represents multiple subnets. For example:
You have these subnets:
``` bash
192.168.1.0/24
192.168.2.0/24
192.168.3.0/24
192.168.4.0/24
```

These can be summarized into:

``` bash
192.168.0.0/22
``` 

## 🧮 How to Calculate Summary Route

  1. Convert all IP addresses to binary.
  2. Find the common prefix among them.
  3. Count the number of common bits → that's your subnet mask.

For example:

    192.168.1.0 → 11000000.10101000.00000001.00000000

    192.168.2.0 → 11000000.10101000.00000010.00000000
    Common bits = first 22 → summary = 192.168.0.0/22

## 📍Where Summary Routing is Used

    On border routers (between autonomous systems)
    In OSPF areas (e.g., summarizing routes from area 1 into area 0)
    In EIGRP with auto-summarization or manual summarization
    
🛠️ Example: Manual Summary Route in Cisco (EIGRP)

```bash
router eigrp 100
 network 192.168.0.0 0.0.3.255
!
interface FastEthernet0/0
 ip summary-address eigrp 100 192.168.0.0 255.255.252.0
```




- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)

