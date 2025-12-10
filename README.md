# First-VM-Network-Enterprise-Home-Lab
A virtualized enterprise network featuring pfSense, Windows Server, Samba, SSH, and XAMPP, with security policies, penetration testing, and documentation.
This repository documents the design, deployment, and security testing of Marc-Anthony Jones’ First Virtual Machine Network, a full enterprise-style lab environment built using VirtualBox, pfSense firewalling, Windows Server 2025, Linux hosts, Samba file sharing, SSH services, and XAMPP web hosting.
The project demonstrates applied skills in network engineering, firewall rule creation, Windows Server administration, Active Directory, VPN security, penetration testing, and security hardening. It also includes formal documentation such as a Network Security Policy, IP Addressing Scheme, Penetration Testing Report, and service-level configurations.
________________________________________
📌 Project Overview
The First VM Network was designed to simulate a realistic small-enterprise environment with:
•	pfSense as the network’s primary firewall
•	Windows Server 2025 providing AD DS, DNS, LDAP, GPOs
•	Linux servers and desktops
•	Samba File Server, SSH Server, and XAMPP Web Server
•	Suricata IDS/IPS
•	MFA enforcement, RBAC, and GPO hardening
•	Penetration testing using Nmap, Hydra, and Nikto
The architecture supports 30 planned hosts, with 10 active and 20 reserved/blocked for future expansion.
(Network Policy Source) 
________________________________________
📡 Network Architecture & Security Controls
Firewall & Traffic Controls
•	pfSense firewall rules implemented for inbound/outbound filtering
•	Suricata IDS/IPS actively monitoring network traffic
•	14 IPs blocked for security isolation
•	MAC filtering enabled to restrict device access
(Policy Source) 
Active Directory & Authentication
•	Centralized authentication using AD DS
•	Custom Organizational Units (OUs) created for access separation
•	Group Policy Objects (GPOs) used for password policies, lockouts, and security settings
•	Default Administrator account disabled
(Policy Source) 
Password & MFA Enforcement
•	Minimum 12-character passwords
•	Required: lowercase, uppercase (not first), number, special character
•	MFA required for admin and VPN accounts
(Policy Source) 
Monitoring & Logging
•	Suricata log monitoring
•	Windows Event Viewer audits
•	Automated security alerts configured
(Policy Source) 
________________________________________
🗃️ Services Implemented
1. Samba File Server
Used for cross-platform file sharing and role-based directory access.
2. SSH Server (Linux)
Configured with:
•	Key-based authentication
•	MFA support
•	Brute-force protection
•	Logging enhancements
3. XAMPP Web Server
Used for hosting testing sites and internal tools, hardened with:
•	Directory permission restrictions
•	Disabled dangerous modules
•	Limited network exposure
________________________________________
🔐 Network Security Policy
A complete JJ’s Computer Solutions Network Security Policy is included.
Key completed tasks include:
•	pfSense firewall deployment
•	Firewall rule creation
•	Active Directory deployment
•	Group Policies (GPO)
•	MFA for admins & remote users
•	Suricata IDS/IPS configuration
•	Windows Server Backup
(Policy Source) 
________________________________________
🛡 Penetration Testing Summary
A formal penetration test was conducted targeting:
•	Windows Server 2025
•	Active Directory
•	VPN
•	pfSense firewall
•	SSH
•	Web services
Key Findings
(Penetration Test Source) 
•	Weak passwords discovered via brute-force
•	Missing security headers on pfSense web server
•	Open ports detected on Windows Server: LDAP, Kerberos, SMB, RPC, DNS
•	Rogue devices detected outside the Static IP Chart
•	VPN brute-force feasible before MFA enforcement
•	MAC spoofing attempt failed, showing strong filtering
Recommendations
•	Harden AD password policies
•	Enforce MFA for VPN (completed)
•	Regularly scan for unknown devices
•	Add security headers to pfSense’s Nginx instance
•	Continue firewall rule tightening
•	Regular quarterly penetration tests
________________________________________
🛰 Nmap Scan Results (Evidence)
192.168.7.1 – pfSense Firewall
•	Open ports: 22, 80, 443
•	Runs Nginx with missing MIME security headers
(Nmap Source) 
192.168.7.7 – Windows Server 2025
•	Open ports include DNS (53), LDAP (389), Kerberos (88), SMB (445), AD Global Catalog
(Nmap Source) 
192.168.7.6 – Kali Linux
•	All TCP ports closed/reset
(Nmap Source) 
________________________________________
📊 IP Addressing Scheme
Your Static IP Chart and Virtual Cloud Network IP Chart document:
•	Device mapping
•	Reserved IPs
•	Blocked IP ranges
•	VM and server addressing structure
(Static IP Chart & VCN Chart provided as repo files.)
________________________________________
⚙️ Repository Structure
First-VM-Network/
│
├── Network Security Policy.docx
├── Penetration Test Report.docx
├── NMAP PenTest.txt
│
├── Samba File Server/
│   └── configuration files
│
├── SSH/
│   └── key-based authentication configs
│
├── XAMPP Web Server/
│   └── htdocs & security configs
│
├── Static IP Chart.csv
└── Virtual Cloud Network IP Chart.xlsx
________________________________________
🎯 Project Outcomes
This project demonstrates professional-level competency in:
•	Network security engineering
•	Firewall configuration and rule design
•	Windows Server + Active Directory administration
•	SSH & Samba service configuration
•	Web server hardening
•	Intrusion detection (Suricata)
•	Penetration testing (Nmap, Hydra, Nikto)
•	Writing security documentation & compliance reports
Your environment mirrors real-world responsibilities of a SOC Analyst, System Administrator, or Network Security Engineer.
________________________________________
🏁 Conclusion
This First VM Network project establishes a functional, secure, and scalable enterprise environment. Through policy development, penetration testing, and service configuration, it provides hands-on experience in:
•	Secure network design
•	Threat detection
•	System hardening
•	Identity and access management
•	Documentation and auditing

