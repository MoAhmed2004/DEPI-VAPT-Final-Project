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
- **Target 1:** Aragog 1.0.2 (Local VM IP: `TBD`) - [VulnHub Link](https://www.vulnhub.com/entry/harrypotter-aragog-102,688/)
- **Target 2:** hacksudo: search (Local VM IP: `TBD`) - [VulnHub Link](https://www.vulnhub.com/entry/hacksudo-search,683/)
- **Authorized Activities:** Port scanning, vulnerability enumeration, exploitation for initial access, and privilege escalation.

### Out-of-Scope
- Denial of Service (DoS) or Distributed Denial of Service (DDoS) attacks.
- Social Engineering attacks.
- Attacking the host operating system or any other devices on the local network.
- Automated exploitation without manual verification.

---

## 3. System Architecture & Setup Environment
To replicate and test this environment, the following setup is required:
- **Hypervisor:** VMware Workstation.
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

*This documentation is continually updated as the testing phases are executed.*
