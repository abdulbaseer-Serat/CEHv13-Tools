# NETWORKWALKS-B083-WK1-PM1-ANDROID-VIRTUALBOX-LAB

> A secure Android-x86 virtual machine deployed in Oracle VirtualBox and connected to the same NAT Network as Kali Linux for cybersecurity lab testing and network communication verification.

---

## 📖 Overview

This project documents the deployment and configuration of an Android-x86 virtual machine within Oracle VirtualBox as part of the Networkwalks Cybersecurity Program.

The Android VM was integrated into the same NAT Network as the Kali Linux workstation, creating a controlled lab environment for testing connectivity, networking, and future cybersecurity exercises.

---

## 🖥️ Lab Environment

### Host Machine

- **Operating System:** Windows 11
- **Hypervisor:** Oracle VM VirtualBox
- **Processor:** Intel Core i7-13620H

### Virtual Machines

| VM | IP Address |
|----|------------|
| Kali Linux | 10.0.0.2 |
| Android-x86 9.0 | 10.0.0.9 |

### Network Configuration

| Setting | Value |
|----------|---------|
| Network Type | VirtualBox NAT Network |
| Network Range | 10.0.0.0/24 |
| Gateway | 10.0.0.1 |
| DNS Server | 8.8.8.8 |

---

## 🏗️ Lab Topology

```text
                    INTERNET
                        |
                        |
                 Gateway 10.0.0.1
                        |
             VirtualBox NAT Network
                  10.0.0.0/24
                        |
        ---------------------------------
        |                               |
        |                               |
   Kali Linux VM                 Android-x86 VM
     10.0.0.2                       10.0.0.9
```

---

# 📸 Screenshots

## 1. Android-x86 ISO Download

images/android-download.png

---

## 2. Virtual Machine Creation

images/virtualbox-create-vm.png

---

## 3. Android Installation

images/android-installation.png

---

## 4. NAT Network Configuration

images/nat-network-config.png

---

## 5. Static IP Configuration

images/android-static-ip.png

---

## 6. Android to Kali Ping Test

images/android-ping-kali.png

---

## 7. Kali to Android Ping Test

images/kali-ping-android.png

---

## 8. Internet Connectivity Test

images/android-internet-test.png

---

# 🚀 Implementation Steps

## Step 1 - Download Android-x86

Downloaded the Android-x86 9.0 ISO image from the official Android-x86 website.

---

## Step 2 - Create a Virtual Machine

Configured:

- VM Name: Android9-Lab
- Type: Linux
- Version: Other Linux (64-bit)
- Memory: 2048 MB
- Storage: 10 GB VDI (Dynamic)

---

## Step 3 - Install Android-x86

Installation settings:

- Filesystem: EXT4
- GRUB Bootloader: Enabled
- System Partition Writable: Yes

---

## Step 4 - Configure Network

Adapter Settings:

```text
Attached To : NAT Network
Network Name: NatNetwork
```

---

## Step 5 - Configure Static Addressing

```text
IP Address  : 10.0.0.9
Subnet Mask : 255.255.255.0
Gateway     : 10.0.0.1
DNS         : 8.8.8.8
```

---

# ✅ Connectivity Verification

## Android → Kali

```bash
ping 10.0.0.2
```

Result:

```text
Reply received successfully
```

✅ PASSED

---

## Kali → Android

```bash
ping 10.0.0.9
```

Result:

```text
Reply received successfully
```

✅ PASSED

---

## Android → Internet

```bash
ping 8.8.8.8
```

Result:

```text
Internet access confirmed
```

✅ PASSED

---

# ⚠️ Challenges Encountered

## Issue 1: Network Communication Failure

### Cause

Incorrect network adapter attachment.

### Fix

Verified that both Kali Linux and Android VMs were connected to the same NAT Network.

---

## Issue 2: Internet Access Not Working

### Cause

Incorrect gateway or DNS values.

### Fix

Configured:

```text
Gateway = 10.0.0.1
DNS = 8.8.8.8
```

---

# 🎯 Skills Learned

- Android-x86 Deployment
- Oracle VirtualBox Administration
- NAT Network Configuration
- Static IPv4 Addressing
- VM-to-VM Communication
- Network Troubleshooting
- Cybersecurity Lab Building

---

# 📂 Repository Structure

```text
