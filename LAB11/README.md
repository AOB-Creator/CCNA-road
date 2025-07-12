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

## 📘 Point-to-Point Interconnection with Subnetting for Host-Specific LANs

The subnet mask determines how many bits are allocated for the network and how many for the hosts.
- A subnet mask is typically represented as /n (CIDR notation), where n is the number of network bits (e.g., /24).
- The remaining bits (32 - n) are used for hosts.

### 📗 2. Number of Hosts per Subnet
🧮 Formula:

```shell
Number of Hosts = 2^(32 - n) - 2
```
## 📙 3. Number of Subnets
If you're subnetting a larger network (like turning a /16 into multiple /24s):

🧮 Formula:
```shell
Number of Subnets = 2^(n - original_mask)
```
From a /16 to /24:
```shell
Number of Subnets = 2^(24 - 16) = 2^8 = 256 subnets
```

## 📕 4. Block Size (Increment) per Subnet
The block size tells you how many IPs each subnet covers.
🧮 Formula:

```shell
Block Size = 256 - last_octet_of_subnet_mask
```


## 🧾 Subnet Summary Table

| CIDR | Subnet Mask       | Hosts (Usable) | Block Size | Network Bits | Host Bits |
|------|-------------------|----------------|------------|---------------|------------|
| /30  | 255.255.255.252   | 2              | 4          | 30            | 2          |
| /29  | 255.255.255.248   | 6              | 8          | 29            | 3          |
| /28  | 255.255.255.240   | 14             | 16         | 28            | 4          |
| /27  | 255.255.255.224   | 30             | 32         | 27            | 5          |
| /26  | 255.255.255.192   | 62             | 64         | 26            | 6          |
| /25  | 255.255.255.128   | 126            | 128        | 25            | 7          |
| /24  | 255.255.255.0     | 254            | 256        | 24            | 8          |
| /23  | 255.255.254.0     | 510            | 512        | 23            | 9          |
| /22  | 255.255.252.0     | 1022           | 1024       | 22            | 10         |
| /21  | 255.255.248.0     | 2046           | 2048       | 21            | 11         |
| /20  | 255.255.240.0     | 4094           | 4096       | 20            | 12         |





- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
