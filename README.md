<a name="top"></a>

![Timeline2_shutterstock_668209624](<[https://www.certocean.com/assets/blog/CCNA-Certification_(2).png](https://yandex-images.clstorage.net/x10km0322/f1a4c8W3vl/BYdoh6xSB1xuTmBxkK9fsXmSCNea6KE_74RPPTWblPR-RKYOz82oG9f4-im6GKx6XaDs9bos37Fw6JausFlltEXfJN7pEwRYZ1wpbYLsT7x00QTByKn1MbW_LUQR7q7eGzWEcOSGrUeD_-Rl-lXHFkSt9a7OXpHuJrqAm7gBPsE_k32vkUhPY0tuLGuwiE2Yd_gi34W-oETrpwVGAP6F9gU3oE3YuKBdocvbKd5y6QQKqeeazHmg4Tq9mLOwPTjWI4pItqpwe1h7VDlrsJNjpm7WDMegiaZZyIkzdRjZpesbHahex56parXOyyflS_kPN5H_qtFspc4LjZ6wrTIa7CeQaaGwZmVEWFwLap-scZ9UyTfQnZGNQvSIFVwz3b78Hgy1TNmOgm-t88w7-E_1HTe2x4nKfbftAZu-kJg1GsMJgl6rkml5aUZLKWO0tFeVScwnwKGrjnTstTRdA_mo4Sc7hFXPvKJMgd3mM8Bn_iEwhdeA516F2iGxipS7JhLpKZFZlJFkanpmWipLsI5NpEfLDdm-iqxI4Iw2fBnvlcYDLrF4_5ueeJbg2BPsT-4QPqfKsNparMU-sJSElyIa9j63eaS6cFBbY0o0a7KYd5hy5Qv1na6ESN6GPkMh4KXbOROwX_2dmm-izeUMw3f6KguU-YHwVpDYJbmdkoQDDcIXs1GUslJjWWJcF1-hpW28R-4r3aaTiWvTpjZQBNmY_yY_i33biZZNverLB9l33iEXt_eUw2mz4y28hZyRPSbtNpZOnItsZHNSTCZjma5KhmfIP92ml5F27JI8cSf2mdsmCqVs4o6cU7TZ7j79dfQ6MZb1ruBxrs4ri5--rTIV6DyTSYCzZVFDR1k7Sb-LWptOyQ_UvLeqQs-nBHU_5bLcBAS1etqxuX2v0swM2WjLEC2xx7rFap_hMba_pKsmGPUjtESskmtZZnJPOEqmklGsTeQV1Jaumk_ShxZOEuo)>)

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

- **User EXEC Mode**: > Limited access; basic monitoring.
- **Privileged EXEC Mode**: # Full access to show/debug commands.
- **Global Configuration Mode**: (config)# Used to make global changes.
- **Interface Configuration Mode**: (config-if)# Used to configure interfaces.
- **VLAN Configuration Mode**: (config-vlan)# VLAN creation and settings.

## 🎓 Console Modes

Network security is the practice of protecting the integrity, confidentiality, and availability of computer networks and data using both hardware and software technologies. It involves implementing policies, controls, and configurations to prevent unauthorized access, misuse, modification, or denial of network resources.

### Basic Switch Configuration

| 🔧 Basic Switch Configuration                        | Configuration Commands |
| :--------------------------------------------------- | :--------------------- |
| MySwitch(config)# line vty 0 4                       | .....                  |
| MySwitch(config-line)# password your_telnet_password | .....                  |
| MySwitch(config-line)# login                         | .....                  |
| MySwitch(config-line)# transport input telnet        | .....                  |
| MySwitch(config-line)# exit                          | .....                  |

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
