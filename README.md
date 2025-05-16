# 🛡️ Ethical Hacking Project: Simulating Real-World Network Exploitation and Defense

**Author:** Swapnil  
**Semester:** 6th  
**Section:** CY6  

This project simulates a real-world network penetration test using open-source tools like **Nmap**, **Metasploit**, and **John the Ripper**. It walks through scanning, enumeration, exploitation, privilege escalation, and remediation techniques, performed in a controlled lab environment.

---

## 📁 Project Contents

- 'CEH_Project_Swapnil.pdf` – Full project report including screenshots and commands used.
- Screenshots of each stage: network scanning, service exploitation, and privilege escalation.

---

## 🎯 Objectives

- Simulate real-world network attacks in a lab environment.
- Learn and practice ethical hacking techniques.
- Identify vulnerabilities and recommend remediation.
- Gain experience with popular cybersecurity tools.

---

## 🛠️ Tools Used

- **Kali Linux** – Attacker Machine
- **Metasploitable** – Target Machine
- **Nmap** – Network Scanning
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
- Suggested updates or deprecation of insecure services.
- Referenced CVEs and official patches.

---

## 📚 Major Learnings

- How to perform active and passive scanning with Nmap.
- Exploiting real vulnerabilities in a safe environment.
- Managing Linux user credentials and cracking passwords.
- Crafting effective remediation strategies for real vulnerabilities.

---

## 📌 Disclaimer

This project is strictly for educational purposes. All activities were performed in a virtual lab environment and should not be conducted on unauthorized networks.

---

## 📸 Preview

![Nmap Scan Output](screenshots/task1.png)  
_Full screenshot documentation available inside the PDF report._

---

## 📎 License

MIT License – feel free to fork, learn, and build upon it!
