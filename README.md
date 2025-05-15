
# Project 1: Scanning and Enumerating a Local Network with Nmap


## 👨‍💻 Author: Swapnil

---

## 🧠 Introduction

In this project, you’ll learn how to use **Nmap**, a powerful network scanning tool, to identify devices and services operating within a local network. Scanning and enumeration are essential skills for ethical hackers, as they assist in recognizing vulnerabilities and gathering vital intel about network infrastructure.

By the end of this project, you’ll be able to:

- Perform basic network scans
- Detect open ports and services
- Gather detailed host information using macOS

---

## 🧾 Pre-requisites

- Basic understanding of IP addresses, ports, and protocols
- Familiarity with using the Terminal on macOS
- Nmap installed via [Homebrew](https://brew.sh/) or MacPorts

---

## 🛠 Lab Set-up and Tools

- **Attacker Machine**: macOS (Terminal)
- **Target Machine**: Local devices or VMs (e.g., Ubuntu VM)
- **Tools Used**:  
  - Nmap  

---

## 🔍 Tasks Breakdown

### Task 1: Basic Network Scan

```bash
nmap -v 192.168.1.0/24
```

Expected Output:
```
Nmap scan report for 192.168.1.5
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http

Nmap scan report for 192.168.1.7
PORT     STATE SERVICE
443/tcp  open  https
```

### Task 2: Reconnaissance

#### 2.1 Hidden Port Scan
```bash
nmap -v -p- 192.168.1.5
```

Expected Output:
```
PORT      STATE SERVICE
22/tcp    open  ssh
80/tcp    open  http
631/tcp   open  ipp
5000/tcp  open  upnp
```

#### 2.2 Service Version Detection
```bash
nmap -v -sV 192.168.1.5
```

Expected Output:
```
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 8.6 (protocol 2.0)
80/tcp   open  http    Apache httpd 2.4.54
631/tcp  open  ipp     CUPS 2.3
5000/tcp open  upnp    Portable SDK for UPnP devices 1.6.25
```

#### 2.3 OS Detection
```bash
sudo nmap -v -O 192.168.1.5
```

Expected Output:
```
Running: Apple macOS 10.15 - 12.5
OS CPE: cpe:/o:apple:mac_os_x
OS details: Apple macOS 10.15.7 (Catalina) or later
```

---

## 📋 Task 3: Enumeration Summary

- **IP**: 192.168.1.5  
- **OS**: macOS Catalina or later  
- **MAC**: B8:E8:56:AA:3C:D1 (Apple Inc.)

---

## ⚔️ Task 4: Exploitation (Theoretical)

> Note: macOS has strong security boundaries, so this is only a hypothetical section.

- **OpenSSH 8.6**: No known major vulnerabilities without local access
- **CUPS**: Older versions vulnerable if exposed publicly
- **UPnP**: Could allow device enumeration in insecure networks

---

## 👤 Task 5: Creating a Local User on macOS

```bash
sudo sysadminctl -addUser swapnil -fullName "Swapnil" -password hello
```

Check with:
```bash
dscl . -read /Users/swapnil
```

---

## 🔓 Task 6: Hash Storage (macOS doesn't store traditional hashes)

> macOS uses a secure keychain system; password hashes are not retrievable like in `/etc/shadow`. Therefore, password cracking isn't straightforward on macOS.

---

## 🛡️ Task 7: Remediation and Fixes

| Service     | Fix/Action                                      |
|-------------|--------------------------------------------------|
| CUPS        | Restrict to local access or disable unused features |
| SSH         | Use key-based authentication; disable root login |
| UPnP        | Disable on networks where not needed              |

---

## 🎓 Learnings

- Used Nmap on macOS for full-range scanning and OS detection  
- Understood enumeration limitations on a secure OS  
- Practiced adding users and verifying system services securely  

---

> **Disclaimer**: This project simulates ethical hacking techniques strictly for educational purposes.
