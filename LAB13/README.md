<a name="top"></a>


![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB13/image.png)

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

🌐 Application Layer & Transport Protocols (TCP/UDP)

#Definition:
This document provides a concise overview of the Application Layer in the OSI model and the TCP/UDP transport protocols

# 📦 Application Layer (Layer 7 - OSI Model)

The Application Layer is the top layer of the OSI model. It provides services directly to the user and enables software applications to communicate over a network.

#✅ Key Responsibilities:

Network services for end-user applications

Data formatting and encoding

Dialog control between applications


### 💬 Common Application Layer Protocols

| Protocol     | Full Name                        | Description                          | Port(s) |
|--------------|----------------------------------|--------------------------------------|---------|
| **HTTP**     | HyperText Transfer Protocol      | Web browsing                         | 80      |
| **HTTPS**    | HTTP Secure                      | Secure web browsing (SSL/TLS)        | 443     |
| **FTP**      | File Transfer Protocol           | Transfers files over a network       | 20, 21  |
| **SFTP**     | SSH File Transfer Protocol       | Secure file transfer                 | 22      |
| **SMTP**     | Simple Mail Transfer Protocol    | Sends emails                         | 25, 587 |
| **IMAP**     | Internet Message Access Protocol | Reads emails from a server           | 143, 993|
| **POP3**     | Post Office Protocol v3          | Downloads emails from a server       | 110, 995|
| **DNS**      | Domain Name System               | Resolves domain names to IP addresses| 53      |
| **DHCP**     | Dynamic Host Configuration Prot. | Assigns IP addresses automatically   | 67, 68  |


#🚚 Transport Layer Protocols (TCP & UDP)

The Transport Layer (Layer 4 in the OSI model) is responsible for end-to-end communication, including reliability, flow control, and data integrity.

#🔹 TCP (Transmission Control Protocol)
TCP is a reliable, connection-oriented protocol.

✅ Features:

    Establishes a connection (3-way handshake)

    Guarantees data delivery and order

    Retransmits lost packets

    Performs error checking and correction

#🔸 UDP (User Datagram Protocol)
UDP is a connectionless, unreliable, but faster protocol.

✅ Features:

    No connection setup

    No guarantee of delivery or order

    Low overhead, minimal latency

### 🔄 TCP vs UDP Comparison

| Feature         | TCP (Transmission Control Protocol)    | UDP (User Datagram Protocol)       |
|-----------------|----------------------------------------|------------------------------------|
| **Type**        | Connection-oriented                    | Connectionless                     |
| **Reliability** | Reliable (acknowledgments, retries)    | Unreliable (no guarantees)         |
| **Speed**       | Slower (due to overhead)               | Faster (minimal overhead)          |
| **Ordering**    | Ensures packets arrive in order        | No guarantee of order              |
| **Error Handling** | Yes (error checking and correction) | Minimal (basic checksum only)      |
| **Use Cases**   | Web, email, file transfer (HTTP, FTP)  | Streaming, gaming, DNS, VoIP       |


## 🌐 Common TCP & UDP Ports

Port numbers are used to **identify specific services** and **direct traffic** to the correct application on a device. They are divided into ranges:

| Range             | Description                           |
|------------------|---------------------------------------|
| 0 – 1023         | **Well-known ports** (reserved by IANA for standard services like HTTP, FTP) |
| 1024 – 49151     | **Registered ports** (used by software applications) |
| 49152 – 65535    | **Dynamic/private ports** (used temporarily for client-side communication) |

---

### 📥 Well-Known Ports (TCP/UDP)

| Port | Protocol | Transport | Description                           |
|------|----------|-----------|---------------------------------------|
| 20   | FTP      | TCP       | File Transfer Protocol (data)         |
| 21   | FTP      | TCP       | File Transfer Protocol (control)      |
| 22   | SSH/SFTP | TCP       | Secure Shell / Secure File Transfer   |
| 23   | Telnet   | TCP       | Remote login (insecure)               |
| 25   | SMTP     | TCP       | Send email                            |
| 53   | DNS      | UDP/TCP   | Domain Name System                    |
| 67   | DHCP     | UDP       | DHCP server to client                 |
| 68   | DHCP     | UDP       | DHCP client to server                 |
| 80   | HTTP     | TCP       | Web browsing                          |
| 110  | POP3     | TCP       | Receive email                         |
| 123  | NTP      | UDP       | Network Time Protocol                 |
| 143  | IMAP     | TCP       | Read email                            |
| 161  | SNMP     | UDP       | Network management protocol           |
| 194  | IRC      | TCP       | Internet Relay Chat                   |
| 443  | HTTPS    | TCP       | Secure web browsing                   |
| 465  | SMTPS    | TCP       | Secure email sending (deprecated)     |
| 993  | IMAPS    | TCP       | Secure IMAP                          |
| 995  | POP3S    | TCP       | Secure POP3                          |
| 3306 | MySQL    | TCP       | MySQL database                        |
| 3389 | RDP      | TCP       | Remote Desktop Protocol               |

---

### 📌 Notes:
- **TCP** is used when reliability and order are critical.
- **UDP** is used when speed is preferred and occasional loss is acceptable.
- Some protocols (like **DNS**) use both TCP and UDP depending on the situation.




- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
