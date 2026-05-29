# MITRE ATT&CK Framework Mapping

## Tactics & Techniques Identified

### Initial Access (TA0001)
| Technique | ID | Implementation |
|-----------|-----|----------------|
| Phishing | T1566 | User executed downloaded payload |

### Execution (TA0002)
| Technique | ID | Implementation |
|-----------|-----|----------------|
| User Execution | T1204.002 | Victim ran payload.exe manually |

### Persistence (TA0003)
| Technique | ID | Implementation |
|-----------|-----|----------------|
| Scheduled Task | T1053.005 | Attempted schtasks creation |
| Registry Run Key | T1547.001 | Attempted HKLM\Run modification |

### Privilege Escalation (TA0004)
| Technique | ID | Implementation |
|-----------|-----|----------------|
| Access Token Manipulation | T1134 | `getsystem` command |
| Bypass User Account Control | T1548.002 | Lab environment bypass |

### Defense Evasion (TA0005)
| Technique | ID | Implementation |
|-----------|-----|----------------|
| Impair Defenses | T1562.001 | Disabled Windows Defender |
| Obfuscated Files | T1027 | Sliver's default obfuscation |

### Credential Access (TA0006)
| Technique | ID | Implementation |
|-----------|-----|----------------|
| OS Credential Dumping | T1003.001 | Registry SAM/SYSTEM access attempt |
| LSASS Memory | T1003.002 | Attempted procdump on lsass.exe |

### Discovery (TA0007)
| Technique | ID | Implementation |
|-----------|-----|----------------|
| Process Discovery | T1057 | `ps` command |
| System Information | T1082 | `info`, `whoami` commands |
| Network Connections | T1049 | `netstat` command |

### Command & Control (TA0011)
| Technique | ID | Implementation |
|-----------|-----|----------------|
| Encrypted Channel | T1573 | mTLS on port 8888 |
| Application Layer Protocol | T1071 | HTTPS over mTLS |

## Detection Opportunities
1. **Network:** Unusual outbound TLS on port 8888
2. **Process:** Unknown executable making beacon connections
3. **File System:** EXE in Downloads with random name
4. **Registry:** Attempted SAM/SYSTEM read attempts

## Mitigation Recommendations
1. Enable PowerShell logging
2. Block unknown outbound ports
3. Monitor LSASS access attempts
4. Application whitelisting
