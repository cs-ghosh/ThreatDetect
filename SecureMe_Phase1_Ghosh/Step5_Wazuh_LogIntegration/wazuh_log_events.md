## **Log Event Collection and Alerting with Wazuh SIEM**

---

## Tasks Completed

### 1. Wazuh Agent Installation

-  Wazuh server installed and configured on Ubuntu VM
-  Wazuh agent installed on:
   - Windows VM
   - kali linux VM
-  Agents connected successfully to Wazuh Manager

---

### 2. Log Sources Configured

#### Linux Agent:
- `/var/log/auth.log`
- `/var/log/syslog`
- `/var/log/dpkg.log`
- `/var/log/sudo.log`

#### Windows Agent:
- Security Event Log 
- System Event Log 
- Application Event Log 
- Setup Log 
- PowerShell Operational Log 

---

### 3. Security Event Simulation

| Test                     | Trigger | Result in Wazuh |
|--------------------------|---------|-----------------|
| Linux failed SSH login   | `ssh testuser@localhost` with wrong password | ✅ Alert shown |
| Windows failed login     | Invalid password from lock screen             | ✅ Alert shown |


---

## Troubleshooting / Pending activities

-  **PowerShell Logs Not Captured:**
 `Microsoft-Windows-PowerShell/Operational` not logging despite log source configured in ossec.conf 
  

-  **Pending activities** 
   - Application & other Events simulation in both linux and windows
   - Revisit Log source configuration in linux and windows

---

