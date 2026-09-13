# 🔐 Cybersecurity Lab Environment Setup

![Cybersecurity](https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000)
![VirtualBox](https://img.shields.io/badge/Ver-VirtualBox%207.2-0070C0?style=flat-square&labelColor=000000)
![Kali Linux](https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white)
![Linux](https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000)
![Network](https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000)
![Penetration Testing](https://img.shields.io/badge/Penetration%20Testing-C000000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white)
![Virtualization](https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000)

> A secure and isolated cybersecurity laboratory built using Oracle VirtualBox and Kali Linux for ethical hacking, network analysis, penetration testing, and cybersecurity training.

---

## 📖 Project Overview

This project documents the setup of a cybersecurity testing lab environment using Oracle VirtualBox and Kali Linux as part of the Networkwalks Cybersecurity Program (Batch B083).

The objective was to build a safe and isolated virtual environment where cybersecurity tools and techniques can be practiced without affecting the host operating system or external networks.

The lab uses a custom VirtualBox NAT Network configured with the subnet:

```text
10.0.0.0/24
```

with Kali Linux configured as the primary security workstation.

---
## 🎯 Objectives

The main objectives of this project are:

- Install and configure Oracle VirtualBox.
- Install and configure Kali Linux.
- Create a private NAT Network for the cybersecurity lab.
- Configure Kali Linux with a static IP address.
- Configure the correct gateway and DNS settings.
- Verify network connectivity.
- Verify DNS resolution and security tools.
- Create a clean snapshot of the configured Kali Linux machine.
- Document the complete lab setup process.
- Prepare the environment for future cybersecurity projects.
# 🖥️ Lab Specifications
---
## ⚙️ Lab Configuration

| **🧩 Component** | **⚙️ Configuration** |
|---|---|
| 🖥️ Host Operating System | Windows 11 |
| 💻 Processor | Intel Core i5-1135G7 |
| 🧠 Host RAM | 8 GB |
| 📦 Hypervisor | VirtualBox 7.2.16 |
| 🐧 Guest OS | Kali Linux 2026.2 |
| 🧠 Kali RAM | 2048 MB |
| 🌐 Network Type | NAT Network |
| 🔗 Network Name | `NatNetwork` |
| 📡 Network Range | `10.0.0.0/24` |
| 💻 Kali IP Address | `10.0.0.2/24` |
| 🚪 Gateway | `10.0.0.1` |
| 🌍 DNS | `8.8.8.8` |
| 📦 DHCP | Enabled |
| 🌐 IPv6 | Disabled |
| 🔢 Future VM Range | `10.0.0.3 – 10.0.0.99` |

---

# 📁 Repository Structure

```text
NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP
│
├── README.md
│
├── screenshots
│   ├── nat-network.png
│   ├── kali-network-adapter.png
│   ├── kali-desktop.png
│   ├── ip-address-verification.png
│   ├── gateway-ping.png
│   ├── internet-ping.png
│   └── dns-resolution.png
│
└── documentation
    └── project-report.pdf
```

---

# 📸 Lab Screenshots

## 1. VirtualBox NAT Network Configuration

**Description**

Created a custom VirtualBox NAT Network using:

<img width="959" height="507" alt="image" src="https://github.com/user-attachments/assets/766c5102-dda4-4003-8f2e-e1abc58cce7b" />


```text
10.0.0.0/24
```

This allows virtual machines to communicate with each other while maintaining internet access.

---

## 2. Kali Linux Network Adapter

screenshots/kali-network-adapter.png

**Description**

Configured Adapter 1 to attach directly to the custom NAT Network.

---

## 3. Kali Linux Desktop

screenshots/kali-desktop.png

**Description**

Successful boot of Kali Linux virtual machine.

---

## 4. IP Address Verification

screenshots/ip-address-verification.png

Command:

```bash
ip a
```

Expected Output:

```text
10.0.0.2/24
```

✅ PASSED

---

## 5. Gateway Connectivity Test

screenshots/gateway-ping.png

Command:

```bash
ping -c 4 10.0.0.1
```

Result:

```text
Successful replies received
```

✅ PASSED

---

## 6. Internet Connectivity Test

screenshots/internet-ping.png

Command:

```bash
ping -c 4 8.8.8.8
```

Result:

```text
External internet access confirmed
```

✅ PASSED

---

## 7. DNS Resolution Test

screenshots/dns-resolution.png

Command:

```bash
nslookup google.com
```

Result:

```text
DNS resolution successful
```

✅ PASSED

---

# ⚠️ Troubleshooting

## Issue: No Internet Access

### Symptoms

- Ping to internet fails
- DNS not resolving

### Solution

Run:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

sudo nmcli connection down "Wired connection 1"

sudo nmcli connection up "Wired connection 1"
```

---

---

# 🎯 Skills Learned

- VirtualBox Administration
- Virtual Networking
- NAT Network Configuration
- Linux Networking
- Static IPv4 Addressing
- DNS Configuration
- VM Snapshot Management
- Cybersecurity Lab Design
- Troubleshooting Network Connectivity

---

# 🔒 Ethical Use Notice

This cybersecurity laboratory was developed exclusively for educational purposes, authorized security training, and ethical hacking practice. All testing should be performed only on systems that you own or have explicit written authorization to assess.

Unauthorized testing against public or private systems is illegal and unethical.

---

# 👨‍💻 Author

**Abdul BASIR-SERAT**

Networkwalks Cybersecurity Program

Batch B083

---

# 🙏 Acknowledgements

Special thanks to:

- Sir Waqas Karim (CCIE)
- Networkwalks Mentorship Team
- Networkwalks Academy

for providing guidance and cybersecurity training throughout this project.
