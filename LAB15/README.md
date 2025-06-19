<a name="top"></a>


![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB15/image.png)

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

## 🔐 Telnet vs SSH – In-Depth Overview

---

### 🌐 What is Telnet?

**Telnet** (Telecommunication Network) is one of the earliest protocols used for remote communication with devices on a network.

#### ⚙️ Key Characteristics:
- **Layer**: Application Layer (OSI Layer 7)
- **Transport Protocol**: TCP
- **Default Port**: `23`
- **Data Transmission**: Plain text (No encryption)
- **Connection Type**: Command-line terminal session

#### 📌 Telnet Use Cases:
- Connecting to legacy network devices
- Testing TCP port availability
- Educational purposes (protocol learning)
- Local network administration (only in secure/internal environments)

#### 🔓 Why Telnet is Insecure:
- Sends **all data unencrypted** — including usernames and passwords
- Vulnerable to **MITM (Man-In-The-Middle)** attacks
- Largely replaced by SSH in modern systems

---

### 🛡️ What is SSH (Secure Shell)?

**SSH** is a modern, secure replacement for Telnet. It allows encrypted command-line access to remote systems.

#### ⚙️ Key Characteristics:
- **Layer**: Application Layer (OSI Layer 7)
- **Transport Protocol**: TCP
- **Default Port**: `22`
- **Data Transmission**: Encrypted using symmetric/asymmetric cryptography
- **Authentication**: Supports both password and public/private key pairs
- **Connection Type**: Encrypted shell session (text-based)

#### 🔐 SSH Use Cases:
- Secure login to Linux/Unix servers
- Managing network devices (routers, switches)
- Automating tasks via shell scripts
- Secure tunneling (port forwarding)
- Secure file transfer using SCP or SFTP

---

### 📂 SSH File Transfer Tools

| Tool     | Purpose                      | Command Example                        |
|----------|------------------------------|----------------------------------------|
| **SCP**  | Secure copy between hosts    | `scp file.txt user@host:/path/`        |
| **SFTP** | Secure FTP over SSH          | `sftp user@host`                       |
| **rsync**| Efficient file syncing over SSH | `rsync -avz file.txt user@host:/path/`|

---

### 🔑 SSH Authentication Methods

| Method        | Description                                               |
|---------------|-----------------------------------------------------------|
| Password      | Login with a remote user’s password (less secure)         |
| Public Key    | Uses a key pair (`id_rsa` and `id_rsa.pub`)               |
| Agent Forwarding | Use your local SSH key to authenticate to remote systems |

---

### 🔍 Network Admin Use Cases

| Task                      | Telnet                | SSH                            |
|---------------------------|-----------------------|---------------------------------|
| Test open TCP port        | `telnet ip port`      | `nc -zv ip port` or `ssh`      |
| Access router CLI         | Only on legacy devices| Secure, encrypted              |
| Automate config scripts   | ❌ Not recommended     | ✅ With Ansible, scripts, etc. |
| File transfer             | ❌ Not supported       | ✅ Via SCP or SFTP             |

---

### 🧪 Telnet Test Examples

```bash
# Test if port 80 is open
telnet example.com 80

# If successful, you’ll get a blank screen or HTTP response

```

---

Let me know if you'd like:
- **Diagrams** (e.g., SSH vs Telnet data flow)
- **Windows vs Linux usage**
- **SSH hardening best practices**
- **SSH server/client setup instructions**

I can provide those too!

## 🔐 Cisco SSH Configuration Steps

This guide shows how to enable **SSH access** on a Cisco switch or router using best practices.

---

### 🧾 Step-by-Step Configuration

```bash
1. Set a hostname (used in key generation)
------------------------------------------------
Switch> enable
Switch# configure terminal
Switch(config)# hostname SW1

2. Create a local user with a password
------------------------------------------------
SW1(config)# username cisco password cisco

3. Define a domain name
------------------------------------------------
SW1(config)# ip domain-name alpamis

4. Generate RSA key pair (1024 or 2048 bits recommended)
------------------------------------------------
SW1(config)# crypto key generate rsa
How many bits in the modulus [512]: 2048

5. Enable SSH on VTY lines (virtual terminal)
------------------------------------------------
SW1(config)# line vty 0 5
SW1(config-line)# transport input ssh
SW1(config-line)# login local
SW1(config-line)# exit

6. (Optional) Set VTY timeout and disable telnet
------------------------------------------------
SW1(config)# line vty 0 4
SW1(config-line)# exec-timeout 10
SW1(config-line)# transport input ssh
SW1(config-line)# exit
```





- **Email**: Send us your inquiries or support requests at [business.alpamis@gmail.com](mailto:business.alpamis@gmail.com).
- **Website**: Visit the official Abblix OIDC Server page for more information: [ADN-SPACE](https://alpamis-adn.vercel.app).

Subscribe to our LinkedIn and Twitter:

[![X](https://img.shields.io/badge/subscribe-white.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTE4LjkwMSAxLjE1M2gzLjY4bC04LjA0IDkuMTlMMjQgMjIuODQ2aC03LjQwNmwtNS44LTcuNTg0LTYuNjM4IDcuNTg0SC40NzRsOC42LTkuODNMMCAxLjE1NGg3LjU5NGw1LjI0MyA2LjkzMlpNMTcuNjEgMjAuNjQ0aDIuMDM5TDYuNDg2IDMuMjRINC4yOThaIi8+PHBhdGggc3R5bGU9ImZpbGw6I2ZmZjtzdHJva2Utd2lkdGg6LjAyMDkyNDEiIGQ9Ik0xMS4wMzYgMTIuMDI4IDQuMzg3IDMuMzM0bC0uMDYtLjA4SDYuNDhsNi41MTYgOC42MTQgNi41NzUgOC42OTQuMDYuMDhoLTIuMDA2eiIvPjwvc3ZnPg==)](https://x.com/AlpamisOmirbek2?t=n_PyU3oFaGuzd31dFO2UfQ&s=09)

We look forward to assisting you and ensuring your experience with our products is successful and enjoyable!

[Back to top](#top)
