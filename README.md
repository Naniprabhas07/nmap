
# 🔐 Cyber Security Internship - Task 1

## 📌 Task: Scan Your Local Network for Open Ports

This repository contains all the necessary files and documentation for **Task 1** of my Cyber Security Internship, which focuses on basic network reconnaissance. The objective is to use **Nmap** to scan the local network for open ports and identify potential vulnerabilities associated with those ports.

---

## 🛠️ Tools Used

- **Nmap** (CLI & Zenmap GUI)
- **Wireshark** *(optional, for packet analysis)*

---

## 🧪 Commands Used

### 1️⃣ TCP SYN Scan (Normal Text Output)
```bash
nmap -sS 192.168.56.1/24 -oN nmap_scan_results.txt

2️⃣ XML Output for HTML Conversion (Optional)

nmap -sS 192.168.56.1/24 -oX scan.xml

3️⃣ Save All Formats at Once

nmap -sS 192.168.56.1/24 -oA myscan

4️⃣ Convert XML to HTML (Optional)

xsltproc scan.xml -o scan.html

> ⚠️ Replace 192.168.56.1/24 with your actual local IP range.




---

📁 Repository Contents

File Name	Description

nmap_scan_results.txt	Human-readable Nmap scan output
services_and_risks.md	List of open ports and associated vulnerabilities
scan.xml (optional)	Nmap results in XML format
scan.html (optional)	HTML report converted from XML
README.md	Documentation of the task, commands, and results



---

📋 Example Nmap Output Summary

PORT     STATE SERVICE
135/tcp  open  msrpc
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds


---

⚠️ Risks Identified from Open Ports

Port	Service	Protocol	Description

135	msrpc	TCP	Microsoft RPC (Remote Procedure Call)
139	netbios-ssn	TCP	NetBIOS Session Service
445	microsoft-ds	TCP	SMB - Microsoft Directory Services



---

🔍 Risk Details

🔓 Port 135 – msrpc

🧨 Risk: Remote Exploitation

Used for: Windows Remote Procedure Call (RPC)

Threats:

Vulnerable to remote code execution

Targeted by the Blaster worm

Often used for lateral movement within a network


Example Exploit: CVE-2003-0352 (Blaster)



---

🔓 Port 139 – netbios-ssn

🧨 Risk: Information Leakage & Unauthorized Access

Used for: NetBIOS over TCP/IP (File/Printer Sharing)

Threats:

Leaks system info (name, shares, domain)

May allow unauthorized file access

Vulnerable to MITM attacks if unsecured


Tools: nbtscan, smbclient, enum



---

🔓 Port 445 – microsoft-ds

🧨 Risk: High-Profile Vulnerabilities

Used for: SMB (Server Message Block), File/Printer sharing

Threats:

Exploited in WannaCry via EternalBlue

Enables remote code execution

Can spread malware within networks


Exploits via: Metasploit, brute-force, SMB relay attacks



---

🔐 Risk Summary Table

Port	Risk Description

135	Remote code execution; RPC-based worm propagation
139	File/share enumeration; MITM attacks
445	SMB exploits like EternalBlue; ransomware entry point



---

✅ Mitigation Recommendations

🔒 Block unused ports via firewall (especially for external traffic)

🧱 Restrict port access to trusted internal IPs

📦 Disable SMBv1 and legacy NetBIOS services if not needed

🔁 Keep systems patched and updated

🔍 Monitor logs and use IDS/IPS for abnormal port activity



---

🧠 Key Concepts Demonstrated

Port scanning with Nmap

TCP SYN scanning

Network host and service discovery

Security risk identification

Basic network reconnaissance

---

> 📝 Disclaimer: All scanning was performed in a safe, local lab environment for educational purposes only. No external networks were targeted