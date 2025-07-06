
## Observation Log – Step 6 

Captured wireshark requests on windows and linux.

**1. Browsing Behavior** - Visited `www.ndtv.com`, DNS resolved to `49.205.2.130` - HTTP GET packets captured in Wireshark 

**2. SSH Session** - SSH login from PuTTY - Wireshark captured handshake - Auth logs in Wazuh confirmed login activity

**3. Script Execution** 
- Executed `wininfo.ps1` powershell command → Output redirected to file 
- Pending troubleshooting on wazuh log collection for Powershell execution

- Executed linuxinfo.sh in linux- Output redirected to file.

**4. Software Installation** 
- Installed VLC on Windows and linux 
- Pending troubleshooting on wazuh log collection for app installation

