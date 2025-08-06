<a name="top"></a>
![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB42/image.png)
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

## ⭐ DHCP Server Configuration – Setup for dynamic IP address allocation

## Overview
This project demonstrates a network setup utilizing a DHCP server for dynamic IP address allocation across multiple subnets, with static routes configured between routers to ensure inter-network communication. The topology includes routers, switches, and various client devices, simulated using a network simulator.

## Network Topology
- **DHCP Server**: Server-PT (IP: 10.10.10.24) located in the 10.10.10.0/24 subnet, responsible for assigning IP addresses.
- **Routers**: 
  - Router0 (Subnets: 10.10.10.0/24, 172.168.1.0/24)
  - Router1 (Subnets: 172.168.1.0/24, 172.168.2.0/24)
  - Router2 (Subnets: 172.168.2.0/24, 172.168.3.0/24)
- **Switches**: Switch3 and others connecting multiple PCs.
- **Client Devices**: PCs (e.g., PC-PT, PC0, PC1) across subnets 172.168.1.0/24, 172.168.2.0/24, 172.168.3.0/24.
- **Interfaces**: FastEthernet (Fa) and GigabitEthernet (Gig) connections.

## Configuration Details

### DHCP Server Configuration
- **IP Address**: 10.10.10.24
- **Scope**: Configures IP ranges for subnets 172.168.1.0/24, 172.168.2.0/24, 172.168.3.0/24.
- **Role**: Dynamically assigns IP addresses to clients in supported subnets.

### Router Configurations
#### Router0
- **Interface Gig0/0**: IP 10.10.10.1, connected to DHCP server subnet.
- **Interface Gig0/1**: IP 172.168.1.1, connected to 172.168.1.0/24.
- **Static Route**: `ip route 172.168.2.0 255.255.255.0 172.168.1.2`
- **IP Helper-Address**: `ip helper-address 10.10.10.24` on Gig0/1 to relay DHCP requests.

#### Router1
- **Interface Gig0/0**: IP 172.168.1.2, connected to Router0.
- **Interface Gig0/1**: IP 172.168.2.1, connected to 172.168.2.0/24.
- **Static Route**: `ip route 172.168.3.0 255.255.255.0 172.168.2.2`
- **IP Helper-Address**: `ip helper-address 10.10.10.24` on Gig0/1.

#### Router2
- **Interface Gig0/0**: IP 172.168.2.2, connected to Router1.
- **Interface Gig0/1**: IP 172.168.3.1, connected to 172.168.3.0/24.
- **Static Route**: `ip route 172.168.1.0 255.255.255.0 172.168.2.1`
- **IP Helper-Address**: `ip helper-address 10.10.10.24` on Gig0/1.

### DHCP and Its Configurations
#### What is DHCP?
- **Dynamic Host Configuration Protocol (DHCP)** is a network management protocol used to automate the assignment of IP addresses and other network configuration parameters to devices on a network. It reduces manual configuration errors and simplifies network administration.

#### Key Features
- **Dynamic IP Allocation**: Assigns IP addresses from a predefined pool to clients for a limited lease time.
- **Automatic Configuration**: Provides additional settings like subnet mask, gateway, and DNS server addresses.
- **Lease Management**: Renews or reassigns IP addresses as needed.

#### DHCP Configuration Details
- **Server Setup**: 
  - **IP Pool**: Define ranges (e.g., 172.168.1.10 - 172.168.1.100 for 172.168.1.0/24).
  - **Subnet Mask**: 255.255.255.0 for all subnets.
  - **Default Gateway**: Set to the router interface IP (e.g., 172.168.1.1 for Router0 Gig0/1).
  - **DNS Server**: Can be set to Server-PT or an external DNS (e.g., 10.10.10.24).
  - **Lease Time**: Configurable duration (e.g., 24 hours) for IP address leases.
- **Command Example (Simulator-Specific)**:
  - `ip dhcp pool SUBNET1`
  - `network 172.168.1.0 255.255.255.0`
  - `default-router 172.168.1.1`
  - `dns-server 10.10.10.24`
  - `lease 1 0 0` (1 day lease).

#### IP Helper-Address
- Configured on router interfaces to forward DHCP broadcast requests to the DHCP server (10.10.10.24).
- Essential for subnets without a local DHCP server, ensuring clients receive IP configurations.













- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
