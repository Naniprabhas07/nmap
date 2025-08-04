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

Let me know if you'd like me to create the services_and_risks.md content too, or help structure your GitHub repo before submission!
