# 🔐 NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP

<div align="center">

### 🛡️ Secure Virtual Cybersecurity Laboratory

Building an isolated environment for Ethical Hacking, Network Analysis, Security Testing, and Cybersecurity Learning

<br>


</div>

---

## 📌 Project Overview

This project documents the design and deployment of a **Cybersecurity Lab Environment** using **Oracle VirtualBox** and **Kali Linux**, completed as part of the **Networkwalks Cybersecurity Program (Batch B083)**.

The objective was to establish a secure and isolated laboratory where cybersecurity tools and techniques can be practiced safely without impacting the host operating system or external networks.

The laboratory is built on a custom **NAT Network (10.0.0.0/24)** and serves as the foundation for future penetration testing, digital forensics, network analysis, and ethical hacking exercises.

---

## 🎯 Project Objectives

✅ Install Oracle VirtualBox

✅ Deploy Kali Linux Virtual Machine

✅ Create a Private NAT Network

✅ Configure Static IPv4 Addressing

✅ Enable Internet Connectivity

✅ Configure DNS Resolution

✅ Verify Gateway Reachability

✅ Enable Shared Clipboard & Shared Folders

✅ Create Baseline VM Snapshots

✅ Build Foundation for Future Cybersecurity Labs

---

# 🏗️ Lab Architecture

```text
                           INTERNET
                               │
                               │
                        Gateway 10.0.0.1
                               │
          ┌──────────────────────────────────┐
          │      VirtualBox NAT Network      │
          │          10.0.0.0/24             │
          └──────────────────────────────────┘
                               │
                               │
                  ┌────────────────────┐
                  │     Kali Linux     │
                  │      10.0.0.2      │
                  └────────────────────┘
```

---

# ⚙️ Lab Configuration

| Component | Configuration |
|------------|---------------|
| 🖥️ Host OS | Windows 11 |
| 💻 CPU | Intel Core i5-1135G7 |
| 🧠 RAM | 8 GB |
| 📦 Hypervisor | Oracle VirtualBox 7.2.16 |
| 🐧 Guest OS | Kali Linux 2026.2 |
| 🌐 Network Type | NAT Network |
| 📡 Network Range | 10.0.0.0/24 |
| 🛜 Kali IP | 10.0.0.2 |
| 🚪 Gateway | 10.0.0.1 |
| 🌍 DNS | 8.8.8.8 |
| 📁 Shared Folder | Downloads |
| 📋 Shared Clipboard | Bidirectional |
| 🔄 Drag & Drop | Bidirectional |

---

# 🧰 Technologies Used

<p align="center">

![Oracle VirtualBox](https://img.shields.io/badge/Oracle_VirtualBox-183A61?style=for-the-badge&logo=virtualbox&logoColor=white)

![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)

![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

![Networking](https://img.shields.io/badge/Networking-008080?style=for-the-badge)

https://img.shields.io/badge/Cybersecurity-Lab-red?style=for-the-badge

![NAT Network](https://img.shields.io/badge/NAT_Networkteal?style=for-the-badge

![Virtualmg.shields.io/badge/Virtualization-Enabled-green?style=for-the-badge

![Status](https://img.shields.io/badge/Status-brightgreen?style=for-the-badge

</p>

---

# 📸 Project Screenshots

## 1️⃣ NAT Network Configuration

images/nat-network.png

Configured an isolated VirtualBox NAT Network using:

```text
10.0.0.0/24
```

---

## 2️⃣ Kali Linux Network Adapter

images/kali-network-adapter.png

Attached Adapter 1 directly to the custom NAT Network.

---

## 3️⃣ Kali Linux Desktop

images/kali-desktop.png

Successful deployment and startup of the Kali Linux Virtual Machine.

---

## 4️⃣ IP Address Verification

images/ip-address-verification.png

```bash
ip a
```

Result:

```text
10.0.0.2/24
```

✅ VERIFIED

---

## 5️⃣ Gateway Connectivity Test

images/gateway-ping.png

```bash
ping -c 4 10.0.0.1
```

✅ PASSED

---

## 6️⃣ Internet Connectivity Verification

images/internet-ping.png

```bash
ping -c 4 8.8.8.8
```

✅ PASSED

---

## 7️⃣ DNS Resolution Test

images/dns-resolution.png

```bash
nslookup google.com
```

✅ PASSED

---

# ✅ Verification Checklist

| Test | Status |
|--------|--------|
| NAT Network Created | ✅ |
| Kali Linux Installed | ✅ |
| Static IP Assigned | ✅ |
| Gateway Reachable | ✅ |
| Internet Access Working | ✅ |
| DNS Resolution Working | ✅ |
| Shared Folder Enabled | ✅ |
| VM Snapshot Created | ✅ |

---

# 🚨 Troubleshooting

### Internet Connectivity Issue

Execute:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

sudo nmcli connection down "Wired connection 1"

sudo nmcli connection up "Wired connection 1"
```

Then restart the virtual machine.

---

# 🎓 Skills Acquired

🔹 Virtualization

🔹 Oracle VirtualBox Administration

🔹 Linux System Administration

🔹 NAT Networking

🔹 Static IP Configuration

🔹 DNS Configuration

🔹 Network Troubleshooting

🔹 Cybersecurity Lab Design

🔹 Snapshot & Recovery Management

---

# 🔒 Ethical Use Statement

This laboratory environment was created exclusively for educational purposes, cybersecurity training, and authorized security research.

All testing activities should only be performed on systems where explicit authorization has been obtained.

---

# 👨‍💻 Author

### Abdul BASIR-SERAT

Cybersecurity Student | Networkwalks Batch B083

---

# 🙏 Acknowledgements

Special thanks to:

✅ Sir Waqas Karim (CCIE)

✅ Networkwalks Mentorship Team

✅ Networkwalks Academy

for their guidance, mentorship, and support throughout this project.

---

<div align="center">

⭐ If you found this project useful, consider giving it a Star.

</div>
