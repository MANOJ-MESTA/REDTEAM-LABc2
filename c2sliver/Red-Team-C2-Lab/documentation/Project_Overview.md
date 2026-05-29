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
