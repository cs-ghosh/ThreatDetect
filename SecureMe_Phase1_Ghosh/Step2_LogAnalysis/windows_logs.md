# Windows Logs Analysis

## Objective
Understand critical Windows event logs using **Event Viewer**. The goal is to extract logs related to system operations, security events, application behavior.

---

## Log Categories & Samples

### 1. **Application Logs**
**Path:** Event Viewer → Windows Logs → Application  
These logs record errors, warnings, and information from applications like Microsoft Office, Chrome, or .NET runtime.

#### Sample Log: Event ID 1000 – Application Error

```
Log Name: Application
Source: Application Error
Date: 07/06/2025 10:45:32 AM
Event ID: 1000
Level: Error
Description: Faulting application name: chrome.exe, version: 91.0.4472.124, faulting module name: ntdll.dll,
exception code: 0xc0000374, fault offset: 0x000e7483, process id: 0x6a0, application start time: 0x01d5f7d1e5e376af.
```
### 2. **Security Logs**
**Path:** Event Viewer → Windows Logs → Security  
Security logs capture audit events such as successful/failed logon attempts, policy changes, and resource access.

####  Sample Log: Event ID 4624 – Successful Logon
```
Log Name: Security
Source: Microsoft-Windows-Security-Auditing
Date: 07/06/2025 09:33:19 AM
Event ID: 4624
Level: Information
Description: An account was successfully logged on.
Logon Type: 2 (Interactive)
Account Name: labuser
Security ID: S-1-5-21-1180699209-877415012-3182924384-1001
Workstation: DESKTOP-WIN10
```
### 3. **System Logs**
**Path:** Event Viewer → Windows Logs → System  
System logs record events from Windows system components like drivers, services, and hardware.

####  Sample Log: Event ID 6006 – System Shutdown

```
Log Name: System
Source: EventLog
Date: 07/06/2025 08:20:10 AM
Event ID: 6006
Level: Information
Description: The Event log service was stopped.
```
