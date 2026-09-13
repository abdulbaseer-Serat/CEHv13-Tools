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

## 4. Lab Architecture

![Lab Architecture]

The Kali Linux VM is connected to a private NAT Network. Additional target machines can be added to the same network for future authorized security testing.

---

## 5. Setup Procedure

### Step 1: Install 7-Zip

7-Zip was installed to extract the Kali Linux virtual-machine files.

### Step 2: Install VirtualBox

Oracle VirtualBox was installed and configured as the virtualization platform.

### Step 3: Create NAT Network

A private NAT Network named **NatNetwork** was created.

**Configuration:**

```text
Network: 10.0.0.0/24
DHCP: Enabled
IPv6: Disabled
```

![NAT Network Configuration]

### Step 4: Import Kali Linux

The Kali Linux VM was imported into VirtualBox and configured with:

```text
Adapter: NAT Network
Network: NatNetwork
RAM: 2048 MB
```

![Kali Linux VM]

A shared folder was also configured for file transfer between the host and Kali VM.

### Step 5: Configure Network

Kali Linux was configured with a consistent IPv4 address:

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

![Kali Network Configuration]

### Step 6: Create Snapshot

After completing the initial configuration, a clean snapshot named **Clean Kali - Network Setup** was created as a recovery point for future experiments.

---

## 6. Lab Verification

The following commands were used to verify the setup:

| Test          | Command                     | Expected Result      |
| ------------- | --------------------------- | -------------------- |
| Check IP      | `ip a`                      | Correct IP displayed |
| Test Gateway  | `ping 10.0.0.1`             | Successful replies   |
| Test Internet | `ping 8.8.8.8`              | Successful replies   |
| Test DNS      | `nslookup networkwalks.com` | Domain resolves      |
| Check Nmap    | `nmap --version`            | Version displayed    |

**Configured IP:** `10.0.0.2/24`
**Gateway:** `10.0.0.1`
**DNS:** `8.8.8.8`

---

## 7. Problem Encountered

### VirtualBox "Can't Open Machine" Error

After extracting the Kali Linux files, VirtualBox displayed a **"Can't Open Machine"** error when I tried to add the VM.

**Solution:**
I switched to the main administrator account on the laptop, opened VirtualBox, and added the extracted Kali VM again. The VM then opened successfully.

---

## 8. What I Learned

* The difference between **NAT and NAT Network**.
* How virtual machines communicate through virtual networks.
* How to configure IPv4, gateway, and DNS settings in Kali Linux.
* How to create and use VirtualBox snapshots.
* The importance of documenting cybersecurity lab configurations and troubleshooting steps.

---

## 9. Security and Ethical Use

This laboratory is intended for **educational purposes and authorized security testing only**.

---

## 10. Tools Used

* 7-Zip
* Oracle VirtualBox
* Kali Linux
  

---

## 11. Conclusion

The virtual cybersecurity laboratory was successfully configured using VirtualBox and Kali Linux. The environment provides a controlled foundation for future cybersecurity and penetration-testing exercises.

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
