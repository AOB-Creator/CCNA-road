<a name="top"></a>
![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB40/image.png)
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

## 🌐 Mastering DHCP: From Basics to Advanced Network Scenarios

## 📘 What is DHCP?
DHCP (Dynamic Host Configuration Protocol) is a network management protocol used to automatically assign IP addresses and other communication parameters (like subnet mask, gateway, DNS) to devices on a network. It greatly reduces the need for manual IP configuration.

## 🔧 How DHCP Works: DORA Process

DHCP operates through a 4-step process known as **DORA**:

| Step | Name        | Description                                                                 |
|------|-------------|-----------------------------------------------------------------------------|
| 1️⃣   | **Discover**  | The client broadcasts a request to locate available DHCP servers.           |
| 2️⃣   | **Offer**     | A DHCP server responds with an available IP address offer.                 |
| 3️⃣   | **Request**   | The client sends a request to accept the offered IP address.               |
| 4️⃣   | **Acknowledge** | The DHCP server acknowledges the request and leases the IP to the client. |


## 🛠️ DHCP Configuration Locations

| Method                  | Description with Configuration Commands                                                                                                                       | Suitable For             |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------|
| **Router DHCP Pool**    | Configure DHCP directly on the router:<br><br>`ip dhcp excluded-address 192.168.1.1 192.168.1.10`<br>`ip dhcp pool LAN_POOL`<br>`network 192.168.1.0 255.255.255.0`<br>`default-router 192.168.1.1`<br>`dns-server 8.8.8.8` | Small to medium networks |
| **Dedicated DHCP Server** | DHCP runs on Windows/Linux server:<br><br>Router must forward requests using:<br>`interface G0/1`<br>`ip helper-address 192.168.2.254`<br>Configure scope on server (e.g. 192.168.2.100–200) | Large enterprise setups  |
| **Multilayer Switch (MLS)** | For each VLAN, create an SVI and DHCP pool:<br><br>`interface vlan 10`<br>`ip address 192.168.10.1 255.255.255.0`<br>`no shutdown`<br><br>`ip dhcp pool VLAN10`<br>`network 192.168.10.0 255.255.255.0`<br>`default-router 192.168.10.1`<br>`dns-server 8.8.8.8`<br>`ip dhcp excluded-address 192.168.10.1 192.168.10.10` | VLAN-segmented networks  |
| **DHCP Relay (Helper Address)** | When the DHCP server is on another network:<br><br>`interface Fa0/1`<br>`ip address 192.168.3.1 255.255.255.0`<br>`ip helper-address 192.168.2.254`<br><br>Make sure routing exists between networks. | Centralized DHCP setup   |



## 🔹 1. Only DHCP Server Configured (No DHCP Service in Use Yet)
- Devices: Server, Switch, 3 PCs
- Status: Only the DHCP server is connected but not yet serving IPs.
- Purpose: Just shows server readiness. No configuration on the switch or clients

## 🔹 2. DHCP Pool on Router
- Devices: Router1, Switch, 3 PCs
- DHCP configuration is done on the router using these commands:

```bash
Router(config)# ip dhcp pool lan_dhcp
Router(dhcp-config)# network 192.168.1.0 255.255.255.0
Router(dhcp-config)# dns-server 8.8.8.8
Router(dhcp-config)# default-router 192.168.1.1
Router(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.10
```

Result: Router assigns IPs from .11 to .254.

## 🔹 3. DHCP Server + IP Helper-Address
- Devices: Server (192.168.2.254), Router2 (interface Fa0/0: 192.168.2.1), Switch, 4 PCs
- The DHCP server is on a different network, so ip helper-address is used on the router interface:

```bash
interface Fa0/1
ip helper-address 192.168.2.254
```
Result: Router forwards DHCP requests to the external DHCP server.

## 🔹 4. DHCP Relay Between Two Routers
- Router3 has DHCP pool
- Router4 has no DHCP pool but forwards DHCP using:

```bash
ip helper-address [Router3's DHCP IP]
```

- PCs connected to Router4’s network get IPs from Router3
- Routing is configured between routers to ensure DHCP communication.

## 🔹 5. Multilayer Switch with VLANs + Multiple DHCP Pools
- Devices: MLS (Layer 3 switch), 4 VLANs (10, 20, 30, 40), 4 PCs
- Each VLAN interface (SVI) has a unique IP and acts as the default gateway.
- 4 DHCP pools configured for each VLAN.

Example for VLAN 10:

```bash
interface vlan 10
ip address 192.168.10.1 255.255.255.0
ip dhcp pool VLAN10
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
```
# 📘 DHCP Configuration Summary

This project demonstrates 5 different DHCP configuration scenarios using Cisco Packet Tracer.

## ✅ Summary Table

| # | Setup Description         | DHCP Location         | Key Configuration / Notes                                                                 |
|---|---------------------------|-----------------------|--------------------------------------------------------------------------------------------|
| 1 | Server Only               | DHCP Server           | Only the server is configured. No IP assignments yet.                                     |
| 2 | Router DHCP Pool          | On Router             | Uses `ip dhcp pool`, `default-router`, `dns-server`, and `excluded-address`.              |
| 3 | DHCP Server with Relay    | External DHCP Server  | Router uses `ip helper-address` to forward requests to the DHCP server.                   |
| 4 | Inter-Router DHCP Relay   | First Router Only     | One router has the DHCP pool. Second uses `ip helper-address` to forward DHCP messages.   |
| 5 | VLAN-Based DHCP (MLS)     | Multilayer Switch     | Each VLAN has its own SVI, default gateway, and DHCP pool. Four separate VLANs are used.  |

---

## 💡 Example Commands

### 🧷 DHCP Pool on Router
```bash
ip dhcp pool LAN_DHCP
 network 192.168.1.0 255.255.255.0
 default-router 192.168.1.1
 dns-server 8.8.8.8
```

















- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
