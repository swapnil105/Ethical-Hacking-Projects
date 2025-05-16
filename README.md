\# 🛡️ Ethical Hacking Project: Simulating Real-World Network
Exploitation and Defense

Author: Swapnil

Semester: 6th

Section: CY6

This project simulates a real-world penetration test in a virtual lab
environment using tools like Nmap, Metasploit, and John the Ripper. It
involves scanning, enumeration, exploitation, privilege escalation,
password cracking, and remediation.

\-\--

Project Contents

\- Polished_CEH_Project_Swapnil.pdf -- Full report with screenshots and
command outputs.

\- Screenshots: Real-time evidence of network attacks and defenses.

\-\--

Objectives

\- Identify system vulnerabilities through simulated attacks.

\- Practice responsible ethical hacking techniques.

\- Learn remediation strategies for discovered weaknesses.

\-\--

Tools Used

\- Kali Linux -- Attacking machine

\- Metasploitable -- Vulnerable target

\- Nmap -- Network and port scanning

\- Metasploit Framework -- Exploitation tool

\- John the Ripper -- Password hash cracking

\-\--

Task Overview and Test Results

Task 1: Basic Network Scanning

Command:

nmap -v 192.168.1.0/24

Result:

Nmap scan report for 192.168.1.10

PORT STATE SERVICE

22/tcp open ssh

80/tcp open http

Nmap scan report for 192.168.1.15

PORT STATE SERVICE

21/tcp open ftp

\-\--

Task 2: Reconnaissance

2.1 Hidden Port Scan

Command:

nmap -v -p- 192.168.1.10

Hidden Ports Found:

\- 8787 (drb)

\- 47436 (mountd)

\- 50918 (java-rmi)

\- 59995 (nlockmgr)

\- 60004 (status)

2.2 Service Version Detection

Command:

nmap -v -sV 192.168.1.10

Result:

21/tcp open ftp vsftpd 2.3.4

22/tcp open ssh OpenSSH 4.7p1 Debian 8ubuntu1

\... (other hidden services)

2.3 OS Detection

Command:

nmap -v -O 192.168.1.10

Result:

Linux 2.6.9 - 2.6.33

\-\--

Task 3: Enumeration Summary

Target IP: 192.168.1.10

MAC Address: 00:0C:29:5D:FE:0B

Open Ports (excluding hidden):

\- 21/tcp -- vsftpd 2.3.4

\- 22/tcp -- OpenSSH 4.7p1

\-\--

Task 4: Exploitation

\- vsftpd 2.3.4: Exploited using exploit/unix/ftp/vsftpd_234_backdoor

\- SMB (Samba 3.0.20): Exploited using usermap_script

\- R Services (rexec, rlogin, rsh): Access gained using legacy tools

\-\--

Task 5: Privilege Escalation

Command Used:

adduser swapnil

Result in /etc/passwd:

swapnil:x:1001:1001:/home/swapnil:/bin/bash

Result in /etc/shadow:

swapnil:\$1\$8nWuasXV\$pk6ZABfqT9NoHv1pPX8Rj.

\-\--

Task 6: Password Hash Cracking

Tool: John the Ripper

Hash File: hashes.txt

Commands:

john hashes.txt

john hashes.txt \--show

Cracked Password: hello

\-\--

Task 7: Remediation

Vulnerability \| Recommendation

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--\|\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

vsftpd 2.3.4 \| Upgrade to version 3.0.5

OpenSSH 4.7p1 \| Upgrade to OpenSSH 9.6

Java RMI \| Disable or restrict via firewall

R Services \| Remove or disable deprecated services

\-\--

Major Learnings

\- Performed deep scans and version detection using Nmap.

\- Used Metasploit for real-world exploitation exercises.

\- Understood Linux user and password management.

\- Practiced safe password cracking and vulnerability patching.

\-\--

Disclaimer

This project is strictly for academic purposes. All testing was done on
isolated VMs with no access to external systems.

\-\--

License

MIT License -- Fork, adapt, or build on it for your own learning.
