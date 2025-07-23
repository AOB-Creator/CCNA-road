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

## ⚙️ Full Cisco Configuration Guide: VLAN Setup, Layer 3 Routing, VTP Modes, and Extended ACLs

This guide provides a complete overview and step-by-step configuration of core Cisco switching and security topics:

- 🔸 VLANs (Virtual LANs) for network segmentation  
- 🔹 Inter-VLAN Routing using Layer 3 (Multilayer) Switches  
- 🔄 VTP (VLAN Trunking Protocol) Server and Client Roles  
- 🔐 Extended Access Control Lists for fine-grained traffic filtering  

Perfect for students, engineers, and network admins working on Cisco Packet Tracer or real Cisco gear.

## 🔐 VLAN ACL Rules – Access Matrix

This table defines the extended ACL rules applied in a multi-VLAN network environment to enforce role-based traffic control.

## 📊 Access Control List (ACL) Table

| VLAN | Source IP Range             | Destination IP       | Protocol | Port(s)     | Action | Description                            |
|------|-----------------------------|----------------------|----------|-------------|--------|----------------------------------------|
| 10   | 192.168.10.1 - 192.168.10.30  | 192.168.100.2        | TCP      | 80, 443     | ✅ Permit | Admins access Web Server 1 (HTTP/HTTPS) |
| 10   | 192.168.10.96 - 192.168.10.126 | 192.168.100.3        | TCP      | 80, 443     | ✅ Permit | Admins access Web Server 2 (HTTP/HTTPS) |
| 20   | 192.168.20.0 - 192.168.20.7   | 192.168.100.5        | TCP      | 21          | ✅ Permit | Developers access FTP Server            |
| 20   | 192.168.20.0 - 192.168.20.7   | 192.168.100.3        | TCP      | 80, 443     | ❌ Deny  | Dev subnet blocked from Web Server 2    |
| 20   | 192.168.20.0 - 192.168.20.127 | 192.168.100.3        | TCP      | 80, 443     | ✅ Permit | Remaining Devs access Web Server 2      |
| 30   | 192.168.30.0 - 192.168.30.3   | 192.168.100.6        | TCP      | 25, 110     | ✅ Permit | Email Dept access SMTP & POP3 Server    |
| 30   | 192.168.30.64 - 192.168.30.95 | 192.168.100.3        | TCP      | 80, 443     | ✅ Permit | Email Dept access Web Server 2          |
| 77   | 192.168.77.0 - 192.168.77.15  | 192.168.100.2        | TCP      | 80, 443     | ✅ Permit | Guests access Web Server 1              |
| All  | Any                          | 192.168.100.4        | UDP      | 53 (DNS)    | ✅ Permit | All VLANs can resolve DNS               |
| All  | Any                          | Any                  | ICMP     | —           | ✅ Permit | ICMP (Ping) allowed between all VLANs   |

---

## 💡 Notes

- **VLAN 100** is the Server Farm (DMZ zone)
- Apply these rules using **Extended ACLs** near the source interface (recommended)
- Use **wildcard masks** in Cisco configuration to match IP ranges
- ACL name suggestion: `SECURITY-ACL`
## Commands

```bash
permit tcp 192.168.10.1 0.0.0.30 host 192.168.100.2 eq www
 permit tcp 192.168.10.1 0.0.0.30 host 192.168.100.2 eq 443
 permit udp any host 192.168.100.4 eq domain
 permit tcp 192.168.10.96 0.0.0.30 host 192.168.100.3 eq 443
 permit tcp 192.168.10.96 0.0.0.30 host 192.168.100.3 eq www
 permit tcp 192.168.20.0 0.0.0.7 host 192.168.100.5 eq ftp
 deny tcp 192.168.20.0 0.0.0.7 host 192.168.100.3 eq www
 deny tcp 192.168.20.0 0.0.0.7 host 192.168.100.3 eq 443
 permit tcp 192.168.20.0 0.0.0.127 host 192.168.100.3 eq 443
 permit tcp 192.168.20.0 0.0.0.127 host 192.168.100.3 eq www
 permit tcp 192.168.30.0 0.0.0.3 host 192.168.100.6 eq smtp
 permit tcp 192.168.30.0 0.0.0.3 host 192.168.100.6 eq pop3
 permit tcp 192.168.30.64 0.0.0.31 host 192.168.100.3 eq www
 permit tcp 192.168.30.64 0.0.0.31 host 192.168.100.3 eq 443
 permit icmp any any
 permit tcp 192.168.77.0 0.0.0.15 host 192.168.100.2 eq www
 permit tcp 192.168.77.0 0.0.0.15 host 192.168.100.2 eq 443
```



## ✅ Step-by-Step: Inter-VLAN Routing on L3 Switch
📌 1. Configure VLANs on the L3 Switch
```bash
Switch(config)# vlan 10
Switch(config-vlan)# name HR
Switch(config-vlan)# exit

Switch(config)# vlan 20
Switch(config-vlan)# name SALES
Switch(config-vlan)# exit
```
📌 2. Assign VLANs to Access Ports
```bash
Switch(config)# interface FastEthernet0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
Switch(config-if)# exit

Switch(config)# interface FastEthernet0/2
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 20
Switch(config-if)# exit
```
📌 3. Enable Routing on the L3 Switch
```bash
Switch(config)# ip routing
```
📌 4. Create SVIs (Switch Virtual Interfaces)
```bash
Switch(config)# interface vlan 10
Switch(config-if)# ip address 192.168.10.1 255.255.255.0
Switch(config-if)# no shutdown
Switch(config-if)# exit

Switch(config)# interface vlan 20
Switch(config-if)# ip address 192.168.20.1 255.255.255.0
Switch(config-if)# no shutdown
Switch(config-if)# exit
```
📌 6. (Optional) Trunk Link to Other Switches
```bash
Switch(config)# interface GigabitEthernet0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 10,20
Switch(config-if)# exit
```
## 🔄 What is VTP?
VTP (VLAN Trunking Protocol) is a Cisco-proprietary Layer 2 protocol that manages VLANs across a switched network.
- It propagates VLAN definitions (IDs, names, etc.) to switches in the same VTP domain.
- Helps centralize VLAN management — create VLANs once on a VTP server, and all clients learn it automatically.

### 🔹 On VTP Server (e.g., Switch-1):
```bash
Switch1(config)# vtp mode server
Switch1(config)# vtp domain MYDOMAIN
Switch1(config)# vtp password cisco
Switch1(config)# vlan 10
Switch1(config-vlan)# name HR
Switch1(config-vlan)# exit
```
### 🔹 On VTP Client (e.g., Switch-2, Switch-3):

```bash
Switch2(config)# vtp mode client
Switch2(config)# vtp domain MYDOMAIN
Switch2(config)# vtp password cisco
```

### 🔹 Set Trunk Ports Between Switches

```bash
SwitchX(config)# interface FastEthernet0/1
SwitchX(config-if)# switchport mode trunk
SwitchX(config-if)# switchport trunk allowed vlan all
```

## 🔐 Extended Access Control Lists (Extended ACLs) - Cisco

Extended Access Control Lists (ACLs) in Cisco are used to filter traffic based on **source/destination IP**, **protocols**, and **port numbers**. This makes them ideal for fine-grained traffic control on enterprise networks.

---

## 🧠 What is an Extended ACL?

An **Extended ACL** allows you to:

- Filter traffic by:
  - Source and Destination IP addresses
  - Protocol types (TCP, UDP, ICMP, etc.)
  - Port numbers (e.g., 80 for HTTP, 443 for HTTPS)
- Permit or deny specific services or hosts

| Criteria         | Example                     |
|------------------|-----------------------------|
| Source IP        | `192.168.1.1`               |
| Destination IP   | `10.0.0.1`                  |
| Protocol         | `tcp`, `udp`, `icmp`        |
| Destination Port | `eq 80`, `eq 443`, etc.     |

---

## 🧠 Placement of Extended ACLs

> 🔺 **Rule of Thumb:**  
> Place Extended ACLs **close to the source** of the traffic you want to **deny**.

| ACL Type     | Placement Recommendation |
|--------------|---------------------------|
| Extended ACL | Close to source           |
| Standard ACL | Close to destination      |

**Why?**  
Placing Extended ACLs near the source prevents unnecessary traffic from traveling across the network.

---

## 🔧 Step-by-Step Configuration

### 🎯 Example Goal:
> Deny HTTP (port 80) from `192.168.1.0/24` to server `10.0.0.5`  
> Allow everything else

### 🧩 1. Define the ACL
```bash
access-list 100 deny tcp 192.168.1.0 0.0.0.255 host 10.0.0.5 eq 80
access-list 100 permit ip any any
```

### 🌐 Block Social Media Access (Simplified)
To block social media sites like Facebook and Instagram by their IP addresses:

```bash
access-list 130 deny tcp any host 157.240.229.35 eq 443   ! facebook.com
access-list 130 deny tcp any host 157.240.201.35 eq 443   ! instagram.com
access-list 130 permit ip any any
```


- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
