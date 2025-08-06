<a name="top"></a>
![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB41/image.png)
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

## 🧠 Multi-Subnet Dynamic IP Network with Static Routing and Simulated Service Infrastructure (DNS, FTP, Mail, Instagram)

## Overview
This project demonstrates a network setup utilizing a DHCP server for dynamic IP address allocation across multiple subnets, with static routes configured between routers to ensure inter-network communication. The topology includes a central router, multiple switches, client PCs, and various servers (DNS, Instagram, FTP, Mail), simulated using a network simulator.

## Network Topology
- **Router**: Router1 (Central router with subnets 10.10.10.0/24, 172.168.1.0/24, 172.168.2.0/24, 8.8.8.0/24)
- **Switches**: Switch0, Switch1, Switch5 connecting multiple devices.
- **DHCP Server**: Implicitly managed via Router1 or an external server (e.g., 10.10.10.24).
- **Servers**:
  - DNS Server-PT (IP: 8.8.8.2)
  - Instagram Server-PT (IP: 8.8.8.24)
  - FTP Server-PT (IP: 8.8.8.3)
  - Mail Server-PT (IP: 8.8.8.4)
- **Client Devices**: PCs (e.g., PC-PT, PC1, PC7, PC8, PC10, PC11, PC12, PC13, PC5, PC6) across subnets 172.168.1.0/24 and 172.168.2.0/24.
- **Interfaces**: FastEthernet (Fa) and GigabitEthernet (Gig) connections.

## Configuration Details

### DHCP Server Configuration
- **IP Address**: Assumed 10.10.10.24 (if external) or managed via Router1.
- **Scope**: Configures IP ranges for subnets 172.168.1.0/24, 172.168.2.0/24.
- **Role**: Dynamically assigns IP addresses to clients in supported subnets.

### Router Configurations
#### Router1
- **Interface Gig0/0**: IP 10.10.10.30, connected to 10.10.10.0/24 (external network or DHCP server).
- **Interface Gig0/1**: IP 172.168.1.24, connected to 172.168.1.0/24 via Switch0.
- **Interface Gig0/2**: IP 172.168.2.24, connected to 172.168.2.0/24 via Switch1.
- **Interface Se0/0/0**: IP 8.8.8.1, connected to 8.8.8.0/24 (server subnet).
- **Static Routes**:
  - `ip route 172.168.2.0 255.255.255.0 172.168.1.24` (if needed for redundancy).
  - `ip route 8.8.8.0 255.255.255.0 8.8.8.1` (default route to server subnet).
- **IP Helper-Address**: `ip helper-address 10.10.10.24` on Gig0/1 and Gig0/2 to relay DHCP requests.

### Server Configurations
- **DNS Server-PT**: IP 8.8.8.2, provides domain name resolution.
- **Instagram Server-PT**: IP 8.8.8.24, hosts web services.
- **FTP Server-PT**: IP 8.8.8.3, handles file transfers.
- **Mail Server-PT**: IP 8.8.8.4, manages email services.

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
  - **Default Gateway**: Set to the router interface IP (e.g., 172.168.1.24 for Router1 Gig0/1).
  - **DNS Server**: Set to 8.8.8.2 (DNS Server-PT).
  - **Lease Time**: Configurable duration (e.g., 24 hours) for IP address leases.
- **Command Example (Simulator-Specific)**:
  - `ip dhcp pool SUBNET1`
  - `network 172.168.1.0 255.255.255.0`
  - `default-router 172.168.1.24`
  - `dns-server 8.8.8.2`
  - `lease 1 0 0` (1 day lease).

#### IP Helper-Address
- Configured on router interfaces (e.g., Gig0/1, Gig0/2) to forward DHCP broadcast requests to the DHCP server (10.10.10.24).

## Setup Instructions
1. **Simulate Network**: Use a network simulator (e.g., Packet Tracer) to replicate the topology.
2. **Configure DHCP Server**: Set up with appropriate IP scopes and lease times.
3. **Configure Router1**: Apply static routes and IP helper-address commands as listed.
4. **Configure Servers**: Assign IPs to DNS, Instagram, FTP, and Mail servers.
5. **Connect Devices**: Attach PCs and switches according to the diagram.
6. **Test Connectivity**: Ping between subnets and to servers to verify routing and DHCP functionality.

## Troubleshooting
- **DHCP Issues**: Ensure `ip helper-address` is correctly set on router interfaces; check DHCP server scope and lease status.
- **Routing Problems**: Verify static route entries and interface IP configurations using `show ip route`.
- **Connectivity**: Check cable connections and interface status with `show ip interface brief`.
- **Verification Commands** (Cisco CLI):
  - `show ip interface brief`: Check interface status.
  - `show ip route`: Verify routing table.
  - `show ip dhcp binding`: Check DHCP lease assignments.
  - `show ip dhcp pool`: Verify DHCP pool settings.
  - `debug ip dhcp server events`: Monitor DHCP events (disable with `no debug`).
  - `ping <IP_ADDRESS>`: Test connectivity.
  - `show running-config`: View current configuration.

## Notes
- All IP addresses and routes are based on the provided network diagram.
- The setup assumes a simulated environment; adjust configurations for real hardware as needed.
- Time of documentation: 03:16 PM +05, Monday, August 04, 2025.


- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
