# 🛡️ Ethical Hacking Project: Simulating Real-World Network Exploitation and Defense

**Author:** Swapnil  
**Semester:** 6th  
**Section:** CY6  



- Simulate real-world network attacks in a lab environment.
- Learn and practice ethical hacking techniques.
- Identify vulnerabilities and recommend remediation.
- Gain experience with popular cybersecurity tools.

---

## 🛠️ Tools Used

- **Kali Linux** – Attacker Machine
- **Metasploitable** – Target Machine
- **Nmap** – Network Scanning
- 
- **Metasploit Framework** – Exploitation
- **John the Ripper** – Password Cracking

---

## ✅ Tasks Performed

### 1. 🔍 Basic Network Scanning
- Identify active hosts and open ports using `nmap -v`.

### 2. 🧭 Reconnaissance
- Full port scans to detect hidden ports.
- Service version detection using `-sV`.
- OS fingerprinting with `-O`.

### 3. 📋 Enumeration
- Listing all detected services and ports (both visible and hidden).
- Collecting OS details and MAC address.

### 4. ⚔️ Exploitation
- **vsftpd 2.3.4** backdoor exploit via Metasploit.
- **SMB** vulnerability (Samba 3.0.20) exploited with `usermap_script`.
- Legacy **R Services** (rexec, rlogin, rsh) exploited using default configs.

### 5. 👤 Privilege Escalation
- Created new user with root permissions.
- Captured `/etc/passwd` and `/etc/shadow` hashes.

### 6. 🔓 Password Cracking
- Cracked password hash using **John the Ripper**.

### 7. 🛡️ Remediation

Target Machine: Local devices or VMs (e.g., Ubuntu VM)
Tools Used:
Nmap
🔍 Tasks Breakdown
Task 1: Basic Network Scan
nmap -v 192.168.1.0/24
Expected Output:

Nmap scan report for 192.168.1.5
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http

Nmap scan report for 192.168.1.7
PORT     STATE SERVICE
443/tcp  open  https
Task 2: Reconnaissance
2.1 Hidden Port Scan
nmap -v -p- 192.168.1.5
Expected Output:

PORT      STATE SERVICE
22/tcp    open  ssh
80/tcp    open  http
631/tcp   open  ipp
5000/tcp  open  upnp
2.2 Service Version Detection
nmap -v -sV 192.168.1.5
Expected Output:

PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 8.6 (protocol 2.0)
80/tcp   open  http    Apache httpd 2.4.54
631/tcp  open  ipp     CUPS 2.3
5000/tcp open  upnp    Portable SDK for UPnP devices 1.6.25
2.3 OS Detection
sudo nmap -v -O 192.168.1.5
Expected Output:

Running: Apple macOS 10.15 - 12.5
OS CPE: cpe:/o:apple:mac_os_x
OS details: Apple macOS 10.15.7 (Catalina) or later
📋 Task 3: Enumeration Summary
IP: 192.168.1.5
OS: macOS Catalina or later
MAC: B8:E8:56:AA:3C:D1 (Apple Inc.)
⚔️ Task 4: Exploitation (Theoretical)
Note: macOS has strong security boundaries, so this is only a hypothetical section.

OpenSSH 8.6: No known major vulnerabilities without local access
CUPS: Older versions vulnerable if exposed publicly
UPnP: Could allow device enumeration in insecure networks
👤 Task 5: Creating a Local User on macOS
sudo sysadminctl -addUser swapnil -fullName "Swapnil" -password hello
Check with:

dscl . -read /Users/swapnil
🔓 Task 6: Hash Storage (macOS doesn't store traditional hashes)
macOS uses a secure keychain system; password hashes are not retrievable like in /etc/shadow. Therefore, password cracking isn't straightforward on macOS.

🛡️ Task 7: Remediation and Fixes
Service	Fix/Action
CUPS	Restrict to local access or disable unused features
SSH	Use key-based authentication; disable root login
UPnP	Disable on networks where not needed
🎓 Learnings
Used Nmap on macOS for full-range scanning and OS detection
Understood enumeration limitations on a secure OS
Practiced adding users and verifying system services securely
Disclaimer: This project simulates ethical hacking techniques strictly for educational purposes.
