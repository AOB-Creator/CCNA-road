<a name="top"></a>


![Timeline2_shutterstoc](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB22/image.png)

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

## 🔷 VTP – VLAN Trunking Protocol

Purpose: VTP is used to manage VLAN configurations centrally across a network of Cisco switches.

---

## ✅ Key Features:
- Centralized VLAN Management: You can create, modify, or delete VLANs on one switch, and the changes are propagated to other switches.
- Reduces Admin Workload: Simplifies management in large networks.
---

## 🔧 VTP Modes

| Mode         | Can Create/Modify VLANs | Receives VLAN Info | Forwards VTP Updates | Stores VLANs in NVRAM | Description |
|--------------|-------------------------|---------------------|-----------------------|------------------------|-------------|
| **Server**    | ✅ Yes                  | ✅ Yes              | ✅ Yes                | ✅ Yes                 | Central control point for VLAN configuration. |
| **Client**    | ❌ No                   | ✅ Yes              | ✅ Yes                | ❌ No                  | Follows the server; can't create or change VLANs. |
| **Transparent** | ✅ Yes (locally only) | ❌ No               | ✅ Yes (forwards only)| ✅ Yes                 | Doesn’t participate in VTP updates, but forwards them. |



## 📦 VTP Domain & Version:

- All switches must be in the same VTP domain name.
- Common versions: VTPv1, VTPv2, VTPv3.
- Uses VTP password for security (optional but recommended).

## 📘 Command Example:

```bash
Switch(config)# vtp domain NetworkLab
Switch(config)# vtp mode server
Switch(config)# vtp password MySecret
```
## 🔧 Multilayer Switch – Trunk Port Configuration

✅ Basic Trunk Port Setup

```bash
Switch(config)# interface GigabitEthernet0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk encapsulation dot1q   # (if required)
Switch(config-if)# switchport trunk allowed vlan 10,20,30
Switch(config-if)# no shutdown

Switch# show interfaces trunk
```

☑️ dot1q is the most common trunking protocol. Some switches (like newer IOS) don’t need the encapsulation command.












- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)

