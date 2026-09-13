# NETWORKWALKS - B083 WK1 PM1 CYBERSECURITY - LAB SETUP

> A secure and isolated cybersecurity laboratory built using Oracle VirtualBox and Kali Linux for ethical hacking, network analysis, penetration testing, and cybersecurity training.

---

# 📖 Project Overview

This project documents the setup of a cybersecurity testing lab environment using Oracle VirtualBox and Kali Linux as part of the Networkwalks Cybersecurity Program (Batch B083).

The objective was to build a safe and isolated virtual environment where cybersecurity tools and techniques can be practiced without affecting the host operating system or external networks.

The lab uses a custom VirtualBox NAT Network configured with the subnet:

```text
10.0.0.0/24
```

with Kali Linux configured as the primary security workstation.

---

# 🖥️ Lab Specifications

## Host Machine

| Component | Details |
|------------|-----------|
| Operating System | Windows 11 |
| Processor | Intel Core i7-13620H |
| Virtualization Platform | Oracle VM VirtualBox |
| Storage | SSD |
| Memory | 16GB+ RAM |

## Kali Linux VM

| Configuration | Value |
|--------------|---------|
| OS | Kali Linux |
| Network Type | NAT Network |
| Static IP | 10.0.0.2 |
| Subnet Mask | 255.255.255.0 |
| Gateway | 10.0.0.1 |
| DNS Server | 8.8.8.8 |

---

# 🌐 Network Architecture

```text
                    INTERNET
                        │
                        │
                Gateway 10.0.0.1
                        │
         ┌──────────────────────────┐
         │  VirtualBox NAT Network  │
         │      10.0.0.0/24         │
         └──────────────────────────┘
                        │
                        │
               Kali Linux VM
                  10.0.0.2
```

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

screenshots/nat-network.png

**Description**

Created a custom VirtualBox NAT Network using:

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

# 🚀 Implementation Steps

## Step 1 – Install VirtualBox

Downloaded and installed Oracle VM VirtualBox.

Official Website:

https://www.virtualbox.org

---

## Step 2 – Create NAT Network

Opened:

```text
File
 └── Tools
      └── Network Manager
```

Created:

```text
NatNetwork
```

Network Address:

```text
10.0.0.0/24
```

DHCP Enabled:

```text
Yes
```

---

## Step 3 – Import Kali Linux

Downloaded the official Kali Linux VirtualBox image and imported it into VirtualBox.

Official Website:

https://www.kali.org/get-kali/

---

## Step 4 – Configure VM Settings

### General

Enabled:

```text
Shared Clipboard = Bidirectional
Drag and Drop = Bidirectional
```

### Shared Folders

Shared Host Folder:

```text
Downloads
```

Auto-Mount:

```text
Enabled
```

---

## Step 5 – Configure Static IP

Kali Linux Network Configuration:

```text
IP Address  : 10.0.0.2
Subnet Mask : 255.255.255.0
Gateway     : 10.0.0.1
DNS         : 8.8.8.8
```

---

## Step 6 – Create Snapshot

Created a clean recovery snapshot named:

```text
Clean Kali Baseline
```

This allows quick rollback after installing tools or performing testing activities.

---

# ✅ Verification Tests

## Interface Verification

```bash
ip a
```

Result:

```text
10.0.0.2/24 assigned
```

✅ PASSED

---

## Gateway Reachability

```bash
ping -c 4 10.0.0.1
```

✅ PASSED

---

## Internet Access Verification

```bash
ping -c 4 8.8.8.8
```

✅ PASSED

---

## DNS Resolution

```bash
nslookup google.com
```

✅ PASSED

---

# ⚠️ Troubleshooting

## Issue 1: No Internet Access

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

## Issue 2: VirtualBox VM Won't Start

### Cause

Hardware virtualization disabled.

### Solution

Enable:

```text
Intel VT-x
```

or

```text
AMD-V
```

from BIOS/UEFI settings.

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
