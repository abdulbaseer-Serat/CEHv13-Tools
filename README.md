# 🛡️ Secure Virtual Cybersecurity Laboratory

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
## 🎯 Objective

The objective of this Week 1 lab was to build and configure a **controlled cybersecurity environment** using Kali Linux and Oracle VirtualBox.

The lab focused on:

- 🔐 Cybersecurity fundamentals
- 🌐 Basic networking
- 🐉 Kali Linux environment setup
- 📡 IP configuration
- 🧪 Network connectivity testing
- 💾 VM snapshot and recovery

The environment provides a safe and controlled space for performing authorized cybersecurity experiments.

---

## 🛡️ Why an Isolated Lab?

A cybersecurity laboratory should be isolated from real-world systems so that experiments can be performed safely.

The isolated environment helps to:

- 🔒 Prevent accidental interaction with external systems
- 🌐 Control communication between lab machines
- 🧪 Safely perform cybersecurity experiments
- 💾 Restore the environment when required

> ⚠️ All activities documented in this repository are performed for educational purposes in an authorized laboratory environment.

---

## 🌐 Network Architecture

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

## 📁 Repository Structure

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

## 📸 Lab Screenshots

### 1. VirtualBox NAT Network Configuration

Created a custom VirtualBox NAT Network using:

<img width="1919" height="1014" alt="nat-network" src="https://github.com/user-attachments/assets/6379d18f-2edc-4da2-8098-a8c3a953d679" />

```text
10.0.0.0/24
```

This allows virtual machines to communicate with each other while maintaining internet access.

---

### 2. Kali Linux Network Adapter

screenshots/kali-network-adapter.png

Configured Adapter 1 to attach directly to the custom NAT Network.

---

### 3. Kali Linux Desktop

screenshots/kali-desktop.png

Successful boot of Kali Linux virtual machine.

---

### 4. IP Address Verification

screenshots/ip-address-verification.png

Command:

```bash
ip a
```

Expected Output:

```text
10.0.0.2/24
```
---

### 5. Gateway Connectivity Test

screenshots/gateway-ping.png

Command:

```bash
ping -c 4 10.0.0.1
```

Result:

```text
Successful replies received
```

---

### 6. Internet Connectivity Test

screenshots/internet-ping.png

Command:

```bash
ping -c 4 8.8.8.8
```

Result:

```text
External internet access confirmed
```

---

### 7. DNS Resolution Test

screenshots/dns-resolution.png

Command:

```bash
nslookup google.com
```

Result:

```text
DNS resolution successful
```

---

## 🚀 Implementation Steps

### Step 1 – Install VirtualBox

Downloaded and installed Oracle VM VirtualBox.

Official Website: https://www.virtualbox.org

```

```
---

### Step 2 – Import Kali Linux

Downloaded the official Kali Linux VirtualBox image and imported it into VirtualBox.

Official Website: https://www.kali.org/get-kali/


---

---

### Step 3 – Configure Static IP

Kali Linux Network Configuration:

```text
IP Address  : 10.0.0.2
Subnet Mask : 255.255.255.0
Gateway     : 10.0.0.1
DNS         : 8.8.8.8
```

---

### Step 4 – Create Snapshot

Created a clean recovery snapshot named:

```text
Clean Kali Baseline
```

This allows quick rollback after installing tools or performing testing activities.

---

## ✅ Verification Tests

### Interface Verification

```bash
ip a
```

Result:

```text
10.0.0.2/24 assigned
```

---

### Gateway Reachability

```bash
ping -c 4 10.0.0.1
```

---

### Internet Access Verification

```bash
ping -c 4 8.8.8.8
```

---

### DNS Resolution

```bash
nslookup google.com
```

---

## ⚠️ Troubleshooting

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

## 🎯 Skills Learned

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

## 🔒 Ethical Use Notice

This cybersecurity laboratory was developed exclusively for educational purposes, authorized security training, and ethical hacking practice. All testing should be performed only on systems that you own or have explicit written authorization to assess.

Unauthorized testing against public or private systems is illegal and unethical.

---

## 👨‍💻 Author

**Abdul BASIR-SERAT**

Networkwalks Cybersecurity Program

Batch B083

---

## 🙏 Acknowledgements

Special thanks to:

- Sir Waqas Karim (CCIE)
- Networkwalks Mentorship Team
- Networkwalks Academy

for providing guidance and cybersecurity training throughout this project.
