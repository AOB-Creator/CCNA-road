<a name="top"></a>
![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB38/image.png)
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

## 🔐 Extended Access Control Lists (ACLs) - Step-by-Step Guide

### 📘 Overview
Extended Access Control Lists (ACLs) provide granular traffic filtering by examining:
- Source & Destination IP addresses
- Protocol (TCP, UDP, ICMP, etc.)
- Source & Destination Ports
- Packet-level details

They are typically applied close to the source to prevent unnecessary traffic on the network.

## ⚙️ Configuration Steps
### 1. Define the Access List

```bash
Router(config)# access-list 110 permit tcp 192.168.10.0 0.0.0.255 any eq 80
Router(config)# access-list 110 deny ip any any
```

### 2. Apply the Access List to an Interface
```bash
Router(config)# interface GigabitEthernet0/0
Router(config-if)# ip access-group 110 in
```

## 🧪 Examples
### Allow HTTP from LAN to Internet, block everything else
```bash
access-list 110 permit tcp 192.168.1.0 0.0.0.255 any eq 80
access-list 110 deny ip any any
interface g0/0
ip access-group 110 in
```
### Allow only SSH to a server (192.168.1.100)
```bash
access-list 111 permit tcp any host 192.168.1.100 eq 22
access-list 111 deny ip any any
interface g0/1
ip access-group 111 in
```
### Block access to social media (e.g. Facebook - IP example)
```bash
access-list 112 deny tcp any host 157.240.22.35 eq 443
access-list 112 permit ip any any
interface g0/0
ip access-group 112 out
```

## 🔍 Verification Commands
```bash
# Show all ACLs
show access-lists

# Show ACL applied to interface
show running-config interface g0/0

# Debug packet filtering (use carefully)
debug ip packet
```

## 🌐 Common Protocols & Port Numbers

| Protocol | Service/Use Case     | Port(s)   | Transport | Direction (Typical) | Description                       |
|----------|----------------------|-----------|-----------|---------------------|-----------------------------------|
| TCP      | HTTP                 | 80        | TCP       | Outbound            | Web traffic                       |
| TCP      | HTTPS                | 443       | TCP       | Outbound            | Secure web traffic                |
| TCP      | SSH                  | 22        | TCP       | Inbound             | Secure remote access              |
| TCP      | Telnet               | 23        | TCP       | Inbound             | Remote terminal access            |
| TCP      | FTP (Control)        | 21        | TCP       | Inbound             | FTP command channel               |
| TCP      | FTP (Data)           | 20        | TCP       | Outbound            | FTP data transfer                 |
| UDP      | DNS                  | 53        | UDP       | Both                | Domain name resolution            |
| TCP      | DNS                  | 53        | TCP       | Inbound             | Large DNS responses (zone xfer)  |
| UDP      | DHCP (Server to Client) | 67     | UDP       | Inbound             | DHCP offer                        |
| UDP      | DHCP (Client to Server) | 68     | UDP       | Outbound            | DHCP discover/request             |
| ICMP     | Echo Request/Reply   | N/A       | ICMP      | Both                | Ping and network diagnostics      |
| UDP      | SNMP (Monitoring)    | 161       | UDP       | Inbound             | Device monitoring & management    |
| UDP      | SNMP Trap            | 162       | UDP       | Outbound            | Alert messages from devices       |
| TCP      | SMTP                 | 25        | TCP       | Outbound            | Sending email                     |
| TCP      | POP3                 | 110       | TCP       | Inbound             | Receiving email (older protocol)  |
| TCP      | IMAP                 | 143       | TCP       | Inbound             | Receiving email (modern)          |
| TCP      | RDP                  | 3389      | TCP       | Inbound             | Remote desktop                    |
| UDP      | NTP                  | 123       | UDP       | Outbound            | Time synchronization              |
| TCP      | MySQL                | 3306      | TCP       | Inbound             | MySQL database access             |
| TCP      | MS SQL Server        | 1433      | TCP       | Inbound             | Microsoft SQL database            |
| TCP      | LDAP                 | 389       | TCP       | Inbound             | Directory services                |
| TCP      | LDAPS (Secure LDAP)  | 636       | TCP       | Inbound             | Secure directory services         |
| TCP      | BGP                  | 179       | TCP       | Inbound/Outbound    | Routing protocol (between routers)|


- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
