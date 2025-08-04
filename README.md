# nmap
This repository contains all the necessary files and documentation for Task 1 of my Cyber Security Internship, which focuses on basic network reconnaissance. The task involved using Nmap to scan the local network for open ports and identifying potential vulnerabilities associated with those ports.

Absolutely! Below is a complete README.md file tailored for your GitHub repository submission for Task 1: Local Network Port Scanning using Nmap — including the commands used, results, risks, and structure.


---

# 🔐 Cyber Security Internship - Task 1

## 📌 Task: Scan Your Local Network for Open Ports

This repository contains files and documentation for *Task 1* of the Cyber Security Internship program. The objective is to perform a basic port scanning operation using *Nmap* and analyze open ports to understand network exposure and potential risks.

---

## 🛠 Tools Used

- *Nmap* (CLI and Zenmap GUI)
- *Wireshark* (optional, for packet analysis)

---

## 🧪 Commands Used

### 🔹 1. TCP SYN Scan (Normal Text Output)
```bash

nmap -sS 192.168.56.1/24 -oN nmap_scan_results.txt

🔹 2. XML Output for HTML Conversion (Optional)

nmap -sS 192.168.56.1/24 -oX scan.xml

🔹 3. Save All Formats at Once

nmap -sS 192.168.56.1/24 -oA myscan

🔹 4. Convert XML to HTML (Optional)

xsltproc scan.xml -o scan.html

> Replace 192.168.56.1/24 with your local network's IP range if different.




---

📁 Repository Contents

File Name	Description

nmap_scan_results.txt	Human-readable Nmap scan output
services_and_risks.md	List of open ports found and associated risks
scan.xml (optional)	XML format of scan results
scan.html (optional)	HTML report converted from XML
README.md	Documentation of task, tools, commands, and results



---

📋 Example Nmap Output Summary

PORT     STATE SERVICE
135/tcp  open  msrpc
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds


---

⚠ Risks Identified from Open Ports

Port	Service	Risk Description

135	msrpc	Remote code execution; exploited by worms like Blaster
139	netbios-ssn	File/share enumeration; vulnerable to MITM and info leaks
445	microsoft-ds	SMB exploits like EternalBlue (WannaCry); critical risk


---

🧠 Key Concepts Covered

Port scanning with Nmap

TCP SYN scan technique

Identifying network devices and services

Recognizing risks from exposed ports

Basic network reconnaissance


This repository was submitted as part of Task 1 for the Cyber Security Internship program.


> 🔐 Note: All IPs and data are from a private lab environment for learning purposes only.



---
Based on Nmap scan, the following ports are open on the host 192.168.56.1:

Port	Service	Protocol	Description

135	msrpc	TCP	Microsoft RPC
139	netbios-ssn	TCP	NetBIOS Session Service
445	microsoft-ds	TCP	Microsoft Directory Services (SMB)


Now let’s break down the risks associated with each:


---

🔓 Port 135 (msrpc - Microsoft RPC)

🧨 Risk: Remote Exploitation

Used for: Windows Remote Procedure Call (RPC).

Threats:

Can be abused for remote code execution.

Target of worms like Blaster.

Often used in lateral movement in internal networks.


Example Exploit: CVE-2003-0352 (Blaster worm used RPC DCOM vulnerability).



---

🔓 Port 139 (netbios-ssn)

🧨 Risk: Information Leakage & Unauthorized Access

Used for: NetBIOS over TCP/IP, file/printer sharing on Windows.

Threats:

Shares system info (computer name, domain, shared folders).

May allow unauthorized file access.

Man-in-the-Middle (MITM) attacks possible if improperly secured.


Exploitable by tools: nbtscan, smbclient, enum.



---

🔓 Port 445 (microsoft-ds - SMB)

🧨 Risk: High-Profile Vulnerabilities

Used for: File and printer sharing (SMB protocol).

Threats:

Famous for EternalBlue exploit (WannaCry ransomware).

Can allow remote code execution, file access, and propagation of malware.

Often scanned and targeted by attackers for vulnerabilities.


Exploitable via: Metasploit, SMB relay attacks, brute-force tools.



---

🔐 Summary of Risks

Port	Risk Description

135	Remote code execution; RPC-based worm propagation
139	File share enumeration; MITM attacks
445	Critical SMB exploits; ransomware entry point



---

✅ Mitigation Recommendations

🔒 Block unused ports via firewall (especially from external access).

🧱 Use firewalls to restrict access to only trusted IPs.

📦 Disable SMBv1 and legacy NetBIOS if not needed.

🔁 Patch systems regularly to fix known vulnerabilities.

🔍 Monitor logs and traffic for unusual behavior or scanning.



---


