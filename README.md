Vulnerability Scanner – Own IP Security Audit (Nessus Essentials)

This project documents a complete vulnerability assessment of my own system using Tenable Nessus Essentials.
The goal of this task was to identify weaknesses, analyze exposure levels, and understand how vulnerability scanning tools work in real-world cybersecurity environments.

📌 Project Overview

This project involves:

Installing and configuring Nessus Essentials

Scanning my local machine’s IP address (192.168.56.1)

Identifying vulnerabilities grouped by severity

Analyzing SMB, SSL, HTTP, RPC, SQL, and system information leakage issues

Generating a final PDF report

Documenting fixes and recommendations

This project is part of my cybersecurity learning tasks and demonstrates hands-on experience in security scanning and assessment.

🏗️ Tools Used
Tool / Technology	Purpose
Nessus Essentials	Vulnerability Scanning
Windows 11 Host	Target System
VirtualBox Host-Only Network	IP: 192.168.56.1
Basic Network Scan Policy	Scan policy used
🖥️ Target Machine Details

OS: Windows 11

Hostname: LAPTOP-G447OS37

IP: 192.168.56.1

SMB Ports: 139, 445 open

Other Services Detected: MySQL (3306), Nessus Web (8834), RPC services

📊 Scan Summary
Severity	Count
Critical	0
High	0
Medium	2
Low	0
Info	78
Total	80
🔍 Medium-Severity Vulnerabilities Found
1. SMB Signing Not Required

Plugin ID: 57608

Risk: Medium

Impact: Allows MITM attacks

Fix:

Enable "Microsoft network server: Digitally sign communications (always)"

Or in Samba: set server signing = mandatory

2. SSL Certificate Cannot Be Trusted

Plugin ID: 51192

Risk: Medium

Impact: MITM attacks possible due to unverified certificate

Fix:

Install a valid certificate issued by a trusted CA

Avoid self-signed certs for production systems

🧾 Informational Findings (Important Ones)

These are not vulnerabilities but give attackers useful information.

✔️ Open Ports Detected

Examples:

135/tcp – RPC

139/tcp – SMB

445/tcp – SMB

3306/tcp – MySQL

8834/tcp – Nessus

Several UDP ports open (137, 138, 1900, 5353, 5355, etc.)

✔️ System Information Exposed

Windows version leak

Hostname leak

NetBIOS domain leaked

SMB and SMB2 dialects supported

MySQL server detected

Device type detected (general-purpose)

🧩 How to Reproduce This Project
1. Install Nessus Essentials

Download from: https://www.tenable.com/products/nessus/nessus-essentials

2. Start Nessus Interface
https://localhost:8834/

3. Create a New Scan

Select Basic Network Scan

Target: 192.168.56.1

Save & Launch

4. Wait for Scan to Complete

My scan took 30 minutes

5. Export Report (PDF/CSV)

Used as final documentation.
