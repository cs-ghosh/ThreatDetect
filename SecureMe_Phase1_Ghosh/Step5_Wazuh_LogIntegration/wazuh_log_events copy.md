# 🔍 Wazuh Log Events Project Summary

## 📁 Project Title:
**Log Event Collection and Alerting with Wazuh SIEM**

---

## ✅ Tasks Completed

### 1. 🖥️ Wazuh Agent Installation
- ✅ Wazuh agent installed on:
  - Windows 10 VM
  - Ubuntu 22.04 VM
- ✅ Wazuh server installed and configured
- ✅ Agents connected successfully to Wazuh Manager

---

### 2. 📥 Log Sources Configured

#### 🪟 Windows Agent:
- [x] Security Event Log
- [x] System Event Log
- [x] Application Event Log
- [x] Setup Log
- [ ] PowerShell Operational Log (Pending - not logging as expected)

#### 🐧 Linux Agent:
- [x] `/var/log/auth.log`
- [x] `/var/log/syslog`
- [x] `/var/log/kern.log`
- [x] `/var/log/dpkg.log`
- [x] `/var/ossec/logs/ossec.log` (Wazuh internal log)

#### 📦 Application Logs:
- [x] Google Chrome (`chrome_debug.log`)
- [ ] Zoom (Not installed / No logs captured)
- [ ] Antivirus (Not available/tested in current setup)

---

### 3. 📸 Screenshots Collected (Sample Set)

| Log Type                 | Screenshot Taken | Description |
|--------------------------|------------------|-------------|
| Wazuh Dashboard          | ✅               | Agent status + alerts |
| File Integrity Check     | ✅               | Linux monitored files |
| Failed Login (Linux)     | ✅               | Alert for SSH login failure |
| Failed Login (Windows)   | ✅               | Windows Event ID 4625 |
| Chrome Log Capture       | ✅               | `chrome_debug.log` sample |

_Screenshots attached in `/screenshots/` folder of repo._

---

### 4. 🔐 Security Event Simulation

| Test                     | Trigger | Result in Wazuh |
|--------------------------|---------|-----------------|
| Linux failed SSH login   | `ssh testuser@localhost` with wrong password | ✅ Alert shown |
| Windows failed login     | Invalid password from lock screen             | ✅ Alert shown |
| Linux sudo attempt       | `sudo ls /root` with user                      | ✅ Alert shown (Event ID 1110) |

---

## ⚠️ Issues and Troubleshooting

- ❌ **PowerShell Logs Not Captured:**
  - Confirmed: Event log `Microsoft-Windows-PowerShell/Operational` not logging despite GPO configuration
  - Potential Fix: Run `gpupdate /force` or check audit policies with `auditpol /get`

- ❗ **Application Logs (Zoom, Antivirus)**:
  - Zoom not installed; Antivirus logs not available due to absence of endpoint protection suite

---

## 🔧 Pending Configuration & Suggestions

| Log Source                      | Action Needed                             |
|---------------------------------|-------------------------------------------|
| PowerShell Script Logging       | Verify log policy, enable script/module logging |
| Windows Application Event Rules | Add custom rules if needed to capture Zoom/AV |
| Sysmon (Optional for Deep Logs) | Consider installing for detailed process/network logs |

---

## 📄 Example Agent Config Snippet

Sample `ossec.conf` log source additions for Windows:

```xml
<localfile>
  <log_format>eventchannel</log_format>
  <location>Microsoft-Windows-PowerShell/Operational</location>
</localfile>

<localfile>
  <log_format>eventchannel</log_format>
  <location>Security</location>
</localfile>

<localfile>
  <log_format>syslog</log_format>
  <location>C:\Users\User\AppData\Local\Google\Chrome\User Data\chrome_debug.log</location>
</localfile>
