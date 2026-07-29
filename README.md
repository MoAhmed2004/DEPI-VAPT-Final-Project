# DEPI VAPT Final Project: Comprehensive Vulnerability Assessment & Server Hardening

## 1. Project Overview & Objectives
This document serves as the complete documentation for the Final Project under the **Digital Egypt Pioneers Initiative (DEPI)**. 
The objective is to perform a full-cycle Vulnerability Assessment and Penetration Testing (VAPT) on two purposely vulnerable machines, followed by a comprehensive server hardening process to mitigate the identified risks.

- **Track:** Vulnerability Analyst and Penetration Testing (VAPT)
- **Target Machines:** HarryPotter: Aragog (1.0.2) & hacksudo: search

---

## 2. Requirements & Rules of Engagement (Scope)
Before initiating any offensive actions, the rules of engagement and scope must be strictly defined to ensure a controlled and authorized testing environment.

### In-Scope (Targets)
- **Target 1:** Aragog 1.0.2 (Lab IP: `192.168.158.128`) - [VulnHub Link](https://www.vulnhub.com/entry/harrypotter-aragog-102,688/)
- **Target 2:** hacksudo: search (Lab IP: `192.168.1.95`) - [VulnHub Link](https://www.vulnhub.com/entry/hacksudo-search,683/)
- **Authorized Activities:** Port scanning, vulnerability enumeration, exploitation for initial access, and privilege escalation.

### Out-of-Scope
- Denial of Service (DoS) or Distributed Denial of Service (DDoS) attacks.
- Social Engineering attacks.
- Attacking the host operating system or any other devices on the local network.
- Automated exploitation without manual verification.

---

## 3. System Architecture & Setup Environment
To replicate and test this environment, the following setup is required:
- **Hypervisor:** Oracle VirtualBox (Better) / VMware Workstation .
- **Attacker Machine:** Kali Linux.
- **Network Configuration:** Both Attacker and Target machines must be configured on the same isolated network (Bridged or NAT) to prevent external interference.
- **Data Flow:** The attacker will initiate traffic via the local network interface, targeting specific exposed ports on the VMs.

---

## 4. Methodology (System Analysis & Design)
This penetration test strictly adheres to the **Penetration Testing Execution Standard (PTES)**, covering the following phases:
1. **Intelligence Gathering:** Network discovery and port scanning.
2. **Vulnerability Analysis:** Identifying CVEs and misconfigurations.
3. **Exploitation:** Gaining initial access to the system.
4. **Post-Exploitation:** Privilege escalation to gain `root`/`SYSTEM` access.
5. **Reporting & Mitigation:** Documenting vulnerabilities and applying server hardening.

---

## 5. Executive Summary of Findings
A total of two virtual machines were assessed, covering a range of critical web application vulnerabilities and Linux privilege escalation vectors.

| Target Machine | Initial Access Vector | Privilege Escalation Vector | Blue Team Hardening Applied |
| :--- | :--- | :--- | :--- |
| **HarryPotter: Aragog (1.0.2)** | WordPress Plugin RCE (`wp-file-manager`) | SUID Binary Execution (`/tmp/bash`) + Root Cron Job | Plugin removal, file permission tightening (`chmod 400`), SUID removal |
| **hacksudo: search** | RFI/LFI via vulnerable PHP parameter + `.env` exposure | SUID Binary + PATH Hijacking (`searchinstall`) | `.env` restriction, input validation, patching insecure `system()` calls |

---

## 6. Comprehensive Documentation & Report
For step-by-step walkthroughs, proof-of-concept execution commands, terminal screenshots, and detailed Blue Team hardening procedures, please refer to the comprehensive project report included in this repository:
**- 📖 [Comprehensive Penetration Testing & Vulnerability Assessment Report](./Comprehensive Penetration Testing Report - DEPI.pdf)
**
---

## 7. Key Takeaways & Purple Team Approach
This project emphasized a **Purple Team methodology**:
1. **Red Team (Offense):** Focused on enumeration, credential reuse, manipulating scheduled tasks, and exploiting environmental variables (`$PATH`).
2. **Blue Team (Defense):** Rather than ending the test at obtaining `root`, practical system administration was performed to remediate the vulnerabilities, enforce principle of least privilege, and secure application-layer configurations.

---

## 8. Project Team & Acknowledgments
This project was successfully executed and documented by the following team members under the **Digital Egypt Pioneers Initiative (DEPI) — Round 4**:
- 👨‍💻 **Mohamed Ahmed**
- 👨‍💻 **Muhammed Shabban**
- 👨‍💻 **Ali Adel**
- 👩‍💻 **Raneem Hany**

**Instructor & Supervisor:** Eng. Ahmed Ashraf  
*Special thanks to our DEPI instructors and mentors for their continuous guidance throughout the Vulnerability Analyst and Penetration Testing track.*
