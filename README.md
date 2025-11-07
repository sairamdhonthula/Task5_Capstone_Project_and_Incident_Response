# Task5_Capstone_Project_and_Incident_Response

# 🧠 Task 5 — Capstone Project & Incident Response  
**Internship:** ApexPlanet — Cybersecurity & Ethical Hacking  
**Intern Name:** Dhonthula Sairam  
**intern id**  :APSPL2519205


**Task:** 5 — End-to-End Cybersecurity Capstone Project  
**Duration:** Final Phase of Internship  
**Mentor:** ApexPlanet Cybersecurity Team  

---

## 📘 Overview
This Capstone project is the culmination of my 60-day Cybersecurity & Ethical Hacking internship with **ApexPlanet Software Pvt. Ltd.**

It integrates everything learned from previous tasks — **reconnaissance, scanning, exploitation, web security, and system hardening** — into a full-scale project involving both **offensive testing** and **defensive response**.

The project simulates a real-world cyber incident — from **attack detection** to **analysis, containment, eradication, and recovery**, followed by an **incident report** and **post-event recommendations**.

---

## 🎯 Objectives
- Conduct a complete **vulnerability assessment and penetration test** on a lab network.  
- Simulate a **cyber attack scenario** and generate an incident response workflow.  
- Build and configure a lightweight **SIEM system (ELK Stack)** for log collection & alerting.  
- Detect, analyze, and respond to security incidents using collected evidence.  
- Document the process in a professional report for management and technical teams.

---

## ⚙️ Lab Architecture

| Component | Role |
|:--|:--|
| **Attacker VM** | Kali Linux (latest) |
| **Target VM** | Metasploitable / DVWA / bWAPP |
| **SIEM Server** | Ubuntu with ELK Stack (Elasticsearch, Logstash, Kibana, Filebeat) |
| **Network Type** | Host-Only isolated lab |
| **Tools Used** | Nmap, Wireshark, Metasploit, OpenVAS, Burp Suite, Filebeat, Elasticsearch, Kibana |

---

## 🧩 Phase 1 — Reconnaissance & Vulnerability Assessment
- **Nmap Scanning:** `sudo nmap -sS -sV -O -oN scan-results/fullscan.txt 192.168.56.102`  
- **Service Enumeration:** Identified FTP (21), SSH (22), HTTP (80).  
- **OpenVAS Scan:** Detected unpatched vsftpd and Apache vulnerabilities (CVSS 8.0+).  
- **Burp Suite Spidering:** Crawled DVWA for input fields and injection points.  
- **Deliverable:** Vulnerability assessment report with risk matrix (High/Medium/Low).

---

## ⚔️ Phase 2 — Exploitation & Post-Exploitation
- Used **Metasploit** to exploit vsftpd 2.3.4 backdoor → reverse shell access.  
- Enumerated users, processes and network connections.  
- Extracted password hashes and cracked weak ones with **John the Ripper**.  
- Captured network packets with **Wireshark** for evidence and timeline analysis.  
- Simulated phishing payload for educational awareness (no malware used).  

---

## 🛡️ Phase 3 — Incident Detection & Response
- Configured **Filebeat** to forward system and auth logs to **Logstash**.  
- Visualized data in **Kibana** dashboards for real-time alerts on failed logins, scans and exploits.  
- Detected a simulated intrusion attempt via unusual SSH login spikes.  
- Conducted root-cause analysis and timeline reconstruction from logs.  
- Implemented response steps: containment (block attacker IP), eradication (remove backdoor), recovery (patch service, rotate passwords).

---

## 🧾 Incident Report (Example Summary)

| Category | Details |
|:--|:--|
| **Incident ID** | APEX-IR-005 |
| **Date** | 2025-10-28 |
| **Detected By** | Kibana Dashboard (Alert Rule) |
| **Type** | Unauthorized SSH Access / Exploit Attempt |
| **Severity** | High |
| **Root Cause** | Weak credential and unpatched service (vsftpd 2.3.4) |
| **Containment** | Firewall rule to block source IP |
| **Eradication** | Removed backdoor, patched vsftpd |
| **Recovery** | Restored services, monitored for 48 hours |
| **Lessons Learned** | Patch early, enforce MFA, centralize logging |

---

## 📊 SIEM Dashboard Highlights
- **Authentication Logs:** Login attempts, success/failure trends.  
- **Network Alerts:** Port scan detection from Nmap.  
- **Vulnerability Tracking:** Top CVEs with severity tags.  
- **Timeline View:** Incident progression (attack → detection → response → recovery).  

All dashboard screenshots are stored in `/screenshots/` folder.

---

## 🔐 Security Hardening & Prevention Steps
- Patch and update critical services immediately after assessment.  
- Disable unused accounts and services.  
- Enforce strong passwords and enable multi-factor authentication.  
- Deploy continuous log monitoring and alerting (SIEM).  
- Conduct user awareness and phishing training regularly.  

---

## 📁 Deliverables
