<a name="top"></a>

![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB19/image.png)

[![OS](https://img.shields.io/badge/OS-linux%2C%20windows%2C%20macOS-0078D4)]()
[![CPU](https://img.shields.io/badge/CPU-x86%2C%20x64%2C%20ARM%2C%20ARM64-FF8C00)]()
[![security rating](https://sonarcloud.io/api/project_badges/measure?project=Abblix_Oidc.Server&metric=security_rating)]()
[![reliability rating](https://sonarcloud.io/api/project_badges/measure?project=Abblix_Oidc.Server&metric=reliability_rating)]()
[![maintainability rating](https://sonarcloud.io/api/project_badges/measure?project=Abblix_Oidc.Server&metric=sqale_rating)](
[![getting started](https://img.shields.io/badge/getting_started-guide-1D76DB)]()
[![Free](https://img.shields.io/badge/free_for_non_commercial_use-brightgreen)](#-license)

⭐ Star us on GitHub — it motivates us a lot!

[![Share](https://img.shields.io/badge/share-000000?logo=x&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-1877F2?logo=facebook&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-0A66C2?logo=linkedin&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-FF4500?logo=reddit&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)
[![Share](https://img.shields.io/badge/share-0088CC?logo=telegram&logoColor=white)](https://github.com/AOB-Creator/CCNA-road)

### 🔐 Port Security on Switch Ports (Static, Dynamic, Sticky + Violations)

##📘 Overview

Port Security is a Layer 2 security feature used on switch interfaces to restrict and control access based on MAC addresses. It helps prevent unauthorized devices from connecting to the network.

## 🧩 Port Security Modes

| Mode     | MAC Learning        | Config Saved | Persistent After Reboot | Flexibility | Use Case                     |
|----------|---------------------|---------------|---------------------------|-------------|------------------------------|
| Static   | Manual              | ✅ Yes        | ✅ Yes                    | ❌ Rigid     | Printers, servers            |
| Dynamic  | Auto (not saved)    | ❌ No         | ❌ No                     | ✅ Flexible  | Temporary user devices       |
| Sticky   | Auto + Saved        | ✅ Yes        | ✅ If saved               | ✅ High      | Office PCs, semi-permanent   |
---

###🔒 Port Security Configuration Steps (Generic)

### Static MAC Binding

```bash
interface FastEthernet0/1
 switchport mode access
 switchport port-security
 switchport port-security mac-address 00AA.BBCC.DDEE
 switchport port-security maximum 1
 switchport port-security violation shutdown
```

### Dynamic MAC Learning (default)

```bash
interface FastEthernet0/1
 switchport mode access
 switchport port-security
 switchport port-security maximum 2
 switchport port-security violation restrict

```

###Sticky MAC Learning

```bash
interface FastEthernet0/1
 switchport mode access
 switchport port-security
 switchport port-security maximum 2
 switchport port-security mac-address sticky
 switchport port-security violation restrict
 
```
## ⚠️ Violation Modes

When the number of learned MAC addresses exceeds the allowed maximum or an unknown MAC tries to access the port, a **violation mode** determines how the switch responds.

| Violation Mode | Behavior                                                                 | Port Status | Logging | Violation Counter |
|----------------|--------------------------------------------------------------------------|-------------|---------|--------------------|
| `protect`      | Drops packets from unauthorized MAC addresses silently.                  | **Stays Up**| ❌ No   | ❌ No              |
| `restrict`     | Drops packets, **logs** the violation, and **increments** violation counter. | **Stays Up**| ✅ Yes  | ✅ Yes          |
| `shutdown`     | Puts the port into **error-disabled** state and shuts it down.           | **Goes Down**| ✅ Yes  | ✅ Yes             |

> 🔧 **Default mode is `shutdown`** – highest security but requires manual or auto recovery.

###Show port security settings for all interfaces

```bash
all interfaces

show port-security

show port-security interface FastEthernet0/1

show port-security address

show mac address-table interface FastEthernet0/1

 
```








- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
