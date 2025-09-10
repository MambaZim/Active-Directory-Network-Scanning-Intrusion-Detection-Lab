# Active-Directory-Network-Scanning-Intrusion-Detection-Lab

## Objective
This project demonstrates a hands-on cybersecurity lab involving Windows Server 2022 and Kali Linux in VirtualBox.
It covers Active Directory setup, network scanning, password attacks, vulnerability assessment, and intrusion detection with Snort.

## Project Overview
- **Tools Used:** VirtualBox, Windows Server 2022, Kali Linux, Wireshark, Nmap, Ncrack, Nessus/OpenVAS (scanner), Snort IDS  
- **Focus Areas:**  
  - Windows Server installation and promotion to Domain Controller
  - Linux VM networking and connectivity
  - Packet capture and analysis with Wireshark
  - Vulnerability scanning and exploitation using Nmap & Ncrack
  - Hardening techniques and defense strategies
  - Intrusion Detection with Snort rules
### Skills Learned
- Proficiency in creating and configuring Windows Server 2022 and Kali Linux virtual machines in VirtualBox.
- Ability to configure static IP addressing, DNS, and network connectivity for lab environments.
- Hands-on experience in promoting a Windows Server to a Domain Controller and managing Active Directory services.
- Practical knowledge of network scanning and OS detection using Nmap.
- Competence in packet capture and analysis with Wireshark, including applying and saving filters.
- Experience installing and configuring OpenSSH Server on Windows Server.
- Ability to perform SSH brute-force testing using ncrack and analyze post-exploitation activities.
- Understanding of firewall rule configuration for securing remote services.
- Experience with vulnerability scanning, identifying weaknesses, and applying remediation steps.
- Development of custom Snort IDS rules to detect suspicious traffic such as SYN scans and SSH connections.
- Strengthened critical thinking and security analysis skills through simulated offensive and defensive security tasks.

### Tools Used
- **VirtualBox** for creating and managing virtual machines.
- **Windows Server 2022** as a target system and domain controller.
- **Kali Linux** as the attacker machine.
- **Wireshark** for packet capture and network traffic analysis.
- **Nmap** for host discovery, OS fingerprinting, and SYN scanning.
- **ncrack** for SSH brute-force testing with password dictionaries.
- **OpenSSH Server** on Windows for secure remote access configuration.
- **Windows Defender Firewall with Advanced Security** for creating inbound firewall rules.
- **Nessus** (or equivalent vulnerability scanner) for vulnerability assessment and remediation planning.
- **Snort IDS** for intrusion detection and custom rule creation.
- **Command-line utilities** (PowerShell, Bash, nano, systemctl) for configuration and testing.

## Steps
**1. Virtual Machine Setup: -**
In this section, I created two virtual machines in VirtualBox:
SRV (Windows Server 2022) with 50GB storage, bridged networking, and configured as a Domain Controller in the deltech.co.za forest.
Kali Linux with static IP configuration for attacker activities.
- **Purpose:** To build a realistic client-server lab environment for both red team (attacker) and blue team (defender) exercises.
<img width="1425" height="771" alt="Picture1" src="https://github.com/user-attachments/assets/03e65369-db0b-492a-8a82-8d773cd5e75f" />

**2. Network Configuration & Connectivity: -**
Windows Server 2022: Configured with static IP 192.168.10.1 and DNS.
Kali Linux: Configured with static IP 192.168.10.2.
Verified connectivity using ping commands from both machines.
- **Purpose:** To ensure both machines could communicate within the same network, enabling testing of attacks and defenses.
<img width="1425" height="771" alt="Picture2" src="https://github.com/user-attachments/assets/5ec0b4ab-c7fd-4a9f-bf4f-d61c5b0ed00b" />

**3. Packet Capture & Network Scanning: -**
Wireshark on Windows Server: Captured live network traffic.
Nmap on Kali Linux: Performed ping sweeps and OS detection scans.
Captured ICMP echo requests/responses and TCP SYN packets in Wireshark.
Applied filters (e.g., ip.addr == 192.168.10.2, tcp.dstport == 53 or 445).
- **Purpose:** To practice network reconnaissance and understand how scanning activity looks in packet captures.
<img width="1425" height="771" alt="Picture3" src="https://github.com/user-attachments/assets/5ca308af-7788-4dab-b412-a8f49e729cb7" />

**4. SSH Configuration & Brute-Force Testing**
Installed and enabled OpenSSH Server on Windows Server.
Configured inbound firewall rules to allow TCP Port 22.
Used ncrack from Kali Linux with a password dictionary to brute-force SSH.
After gaining access, executed post-exploitation actions like creating a file on the server desktop.
- **Purpose:** To simulate a realistic attack scenario and understand how weak credentials can be exploited.
<img width="1425" height="771" alt="Picture5" src="https://github.com/user-attachments/assets/54b91742-daf5-4ec0-9d68-c46018b7542c" />

**5. Vulnerability Scanning**
Created and ran a scan policy called “First Scan” against Windows Server.
Identified vulnerabilities such as missing patches, default passwords, unnecessary services, and weak configurations.
Reviewed remediation steps (patching, strong passwords, disabling services, hardening configs).
- **Purpose:** To learn how vulnerability assessment helps identify and fix weaknesses before they can be exploited.
<img width="1425" height="771" alt="Picture6" src="https://github.com/user-attachments/assets/3c657e0d-f658-406f-a767-51e952dd107b" />

**6. Intrusion Detection with Snort**
Configured Snort IDS rules on Windows Server:
Rule to detect repeated SSH attempts.
Rule to detect SYN scans from Nmap.
Ran Snort in console mode to monitor traffic.
From Kali, performed scans and SSH login attempts → Snort generated alerts.
- **Purpose:** To simulate how a defender can detect attacks using IDS signatures and logs.
<img width="1425" height="771" alt="Picture7" src="https://github.com/user-attachments/assets/2a9e6521-2ed0-4f2e-b19d-5a5c6261ac6c" />

**7. Attack/Defense Analysis**
Attacker’s Perspective: Used Kali Linux to perform reconnaissance, brute-force SSH, and gain unauthorized access.
Defender’s Perspective: Used Wireshark, Firewall, Snort, and Vulnerability Scanners to detect and mitigate these attacks.
- **Purpose:** To understand both offensive and defensive security techniques in a controlled lab.
<img width="1425" height="771" alt="Picture8" src="https://github.com/user-attachments/assets/c8a01a1d-fe8a-47de-959c-ac2ba603366e" />
<img width="1425" height="771" alt="Picture9" src="https://github.com/user-attachments/assets/ad9bf7eb-7d9b-4197-9f4d-c21b140792ca" />






