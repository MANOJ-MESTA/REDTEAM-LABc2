Red Team C2 Infrastructure Lab
Project Overview
Professional red team simulation using Sliver C2 framework to establish encrypted command & control channel with Windows 10 target.

Lab Architecture
┌─────────────┐ mTLS:8888 ┌─────────────┐ │ Kali │ ◄──────────────────────► │ Windows 10 │ │ (C2 Server)│ Beacons │ (Victim) │ │ 192.168.56.102│ │ 192.168.56.20│ └─────────────┘ └─────────────┘

Tools Used
C2 Framework: Sliver v1.5.42
Listener: mTLS (Mutual TLS - Encrypted)
Implant Type: Windows x64 Executable
Transfer Method: Python HTTP Server
Key Achievements
Deployed encrypted mTLS C2 channel
Obtained ADMINISTRATOR level access
Escalated to NT AUTHORITY\SYSTEM
Performed process & network enumeration
Attempted credential harvesting via registry
MITRE ATT&CK Techniques
Tactic	Technique ID	Technique Name
Command & Control	T1573	Encrypted Channel
Privilege Escalation	T1134	Access Token Manipulation
Discovery	T1057	Process Discovery
Discovery	T1082	System Information Discovery
Credential Access	T1003	OS Credential Dumping
Screenshots
View all screenshots

Lessons Learned
Windows Defender immediately blocks default payloads
IP changes require payload regeneration
SYSTEM access enables complete host compromise
Multiple sessions create noise - always clean up
Project Complete
This lab demonstrates full C2 lifecycle: deployment → beacon → privilege escalation → post-exploitation
