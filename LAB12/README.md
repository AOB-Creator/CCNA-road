<a name="top"></a>


![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB12/image.png)

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

🔥 🚀 Cisco Networking: Switch Configurations & Console Modes📑

## Table of Contents
- [Telnet](#-about)
- [Console Modes](#-consolemodes)
- [Basic Switch Configuration](#-basicswitchconfig)
- [Saving Configurations](#-saveconfig)
- [Feedback and Contributions](#-feedback-and-contributions)
- [License](#-license)
- [Contacts](#%EF%B8%8F-contacts)


## 🚀 About

Welcome to the Cisco Networking Configuration Guide — a comprehensive resource to help you understand and implement essential Cisco switch configurations and master console modes for managing your network efficiently.

## ✅ Summary Table

| Tool/Concept     | Purpose                                             | Example Use             |
|------------------|-----------------------------------------------------|--------------------------|
| **IP + Subnet**  | Divide network and host portions                    | `192.168.1.10/24`        |
| **CIDR**         | Compact subnet representation                       | `/24`, `/16`, `/8`       |
| **Traceroute**   | Show packet path to destination                     | `traceroute google.uz`   |
| **Loopback**     | Test local system networking                        | `ping 127.0.0.1`         |
| **Netstat**      | Show network connections and ports                  | `netstat -an`            |
| **Route Print**  | View routing table and gateway paths                | `route print` (Windows)  |


## 🧭 Traceroute (Trace the Path to a Host)

```shell
traceroute google.uz
```
Purpose:

    Shows the path packets take to reach a destination.

    Helps diagnose network delays or routing problems.

### 📌 IP Address Division (with Subnet Mask & CIDR)
    IP Address is a unique identifier for a device on a network. It’s typically written as four octets (e.g., 192.168.1.10).

    Subnet Mask defines how the IP address is split between the network and host parts. Example:

        255.255.255.0 → Network: 192.168.1, Host: .10

    CIDR (Classless Inter-Domain Routing) is a compact representation of a subnet mask. Example:

        192.168.1.10/24 means the first 24 bits are network bits, equivalent to 255.255.255.0.

### 🔁 Loopback Address (127.0.0.1)

	127.0.0.1 is the loopback address that points to your own machine.

	Used for testing network software without actually sending data over the network.

	Alias: localhost
	
### 📡 Netstat (Network Statistics)

	Command: netstat (use netstat -an for detailed output)
```shell
	netstat -an
	netstat -r
```
	Purpose:

	Displays active connections, listening ports, routing tables, and network statistics.

	Helps identify open ports and detect suspicious activity.


## 📝 How to Build

To build the packages, follow these steps:

```shell
🌀️ Type of Modes
1. switch> 📡 User EXEC Mode
2. switch# 📡 Privileged EXEC Mode
3. switch(configure)# 📡 Global Configuration Mode
4. switch(configure-if)#  📡 Additional Sub-Modes:

✅  Changing modes
switch> - switch#
switch> enable

switch# -> switch(configure)#
switch# configure terminal

switch(config)#  ->  switch (config-if)# 
switch(config)# interface FastEthernet0/1

📡 Privileged EXEC Mode
switch# show running-config
switch# show ip interface brief
switch# show version
switch# copy running-config startup-config
switch# write
switch# reload

📡 TELNET setting ⬇️
MySwitch(config)# line vty 0 4
MySwitch(config-line)# password your_telnet_password
MySwitch(config-line)# login
MySwitch(config-line)# transport input telnet
MySwitch(config-line)# exit

📡Mac and Route table📡
switch> show mac-address-table
switch# erase running-config
switch(config) ip default-gateway 192.168.2.1

📡Static IP route📡
R1: ip route 192.168.3.0 255.255.255.0  fa 0/1
R2: ip route 192.168.1.0 255.255.255.0  fa 0/1
Router#: show ip route
```


- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
