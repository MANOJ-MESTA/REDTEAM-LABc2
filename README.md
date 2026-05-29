
# 🎯 Red Team C2 Infrastructure Lab

## Project Overview
Professional red team simulation using Sliver C2 framework to establish encrypted command & control channel with Windows 10 target.

## Lab Architecture
┌─────────────┐ mTLS:8888 ┌─────────────┐
│ Kali │ ◄──────────────────────► │ Windows 10 │
│ (C2 Server)│ Beacons │ (Victim) │
│ 192.168.56.102│ │ 192.168.56.20│
└─────────────┘ └─────────────┘

text

## Tools Used
- **C2 Framework:** Sliver v1.5.42
- **Listener:** mTLS (Mutual TLS - Encrypted)
- **Implant Type:** Windows x64 Executable
- **Transfer Method:** Python HTTP Server

## Key Achievements
- ✅ Deployed encrypted mTLS C2 channel
- ✅ Obtained ADMINISTRATOR level access
- ✅ Escalated to NT AUTHORITY\SYSTEM
- ✅ Performed process & network enumeration
- ✅ Attempted credential harvesting via registry

## MITRE ATT&CK Techniques
| Tactic | Technique ID | Technique Name |
|--------|--------------|----------------|
| Command & Control | T1573 | Encrypted Channel |
| Privilege Escalation | T1134 | Access Token Manipulation |
| Discovery | T1057 | Process Discovery |
| Discovery | T1082 | System Information Discovery |
| Credential Access | T1003 | OS Credential Dumping |

## Screenshots
📸 [View all screenshots](./screenshots/)

## Lessons Learned
1. Windows Defender immediately blocks default payloads
2. IP changes require payload regeneration
3. SYSTEM access enables complete host compromise
4. Multiple sessions create noise - always clean up

## 🏆 Project Complete
This lab demonstrates full C2 lifecycle: deployment → beacon → privilege escalation → post-exploitation
📄 documentation/Project_Overview.md
markdown
# Project Overview

## Objective
Build a professional red team C2 infrastructure from scratch, deploy encrypted implant, and perform post-exploitation on Windows 10.

## Why This Project?
- Real red team workflow (not just Metasploit)
- Industry standard C2 framework (Sliver)
- Resume-worthy technical depth
- MITRE ATT&CK mapping shows strategic thinking

## Scope
- ✅ Deploy C2 server with encrypted listener
- ✅ Generate & deliver custom implant
- ✅ Bypass Windows Defender (lab environment)
- ✅ Obtain reverse session with admin privileges
- ✅ Escalate to SYSTEM
- ✅ Perform post-exploitation enumeration
- ✅ Document all steps with screenshots

## Tools & Versions
| Tool | Version | Purpose |
|------|---------|---------|
| Kali Linux | 2024.x | C2 Server |
| Windows 10 | 22H2 | Target |
| Sliver | v1.5.42 | C2 Framework |
| VirtualBox | 7.x | Lab environment |

## Results Summary
- **Sessions Obtained:** 8+ active beacons
- **Privilege Level:** NT AUTHORITY\SYSTEM
- **C2 Protocol:** mTLS (encrypted)
- **Detection Status:** Defender bypassed (lab only)
