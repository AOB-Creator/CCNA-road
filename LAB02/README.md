<a name="top"></a>
![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB02/image.png)
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
- [About](#-about)
- [Console Modes](#-consolemodes)
- [Basic Switch Configuration](#-basicswitchconfig)
- [Saving Configurations](#-saveconfig)
- [Feedback and Contributions](#-feedback-and-contributions)
- [License](#-license)
- [Contacts](#%EF%B8%8F-contacts)


## 🚀 About

Welcome to the Cisco Networking Configuration Guide — a comprehensive resource to help you understand and implement essential Cisco switch configurations and master console modes for managing your network efficiently.

- **User EXEC Mode**: > Limited access; basic monitoring.
- **Privileged EXEC Mode**: # Full access to show/debug commands.
- **Global Configuration Mode**: (config)# Used to make global changes.
- **Interface Configuration Mode**: (config-if)# Used to configure interfaces.
- **VLAN Configuration Mode**: (config-vlan)# VLAN creation and settings.

Switch> enable
Switch# configure terminal
Switch(config)# interface FastEthernet0/1
Switch(config-if)#

## 🎓 Console Modes

Network security is the practice of protecting the integrity, confidentiality, and availability of computer networks and data using both hardware and software technologies. It involves implementing policies, controls, and configurations to prevent unauthorized access, misuse, modification, or denial of network resources.

### Basic Switch Configuration
|🔧 Basic Switch Configuration | Configuration Commands |
|:-|:-|:-|
| enable | .....|
| configure terminal | ..... |
| hostname SW1 | ..... |
| no ip domain-lookup | ..... |
| enable secret cisco123 | ..... |
| line console 0 | ..... |
| password console123 | ..... |
| login | ..... |
| exit | ..... |
| write memory | ..... |
| copy running-config startup-config | ..... |

### Saving Configurations


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

📡 Global Configuration Mode ⬇️
switch(config)# hostname 1cisco_floor
1cisco_floor(config)# nohostname
switch(config)# enable password cisco
switch(config)# enable secret password cisco
switch(config)# no enable password
switch(config)# no enable secret
switch(config)# line console 0
switch(config)# service password-encryption
switch(config)# banner motd #Unauthorized access is prohibited#
switch(config)# interface vlan 1
switch(config)# no shutdown
switch(config)# ip address 192.168.1.100 255.255.255.0

```


- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
