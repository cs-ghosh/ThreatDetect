# UFW Firewall Rules Documentation

This document captures the Uncomplicated Firewall (UFW) configuration applied to the Linux system.

---

## UFW Installation & enable

```bash
sudo apt update
sudo apt install ufw
sudo ufw enable
```
---
## Default Policies

```bash
sudo ufw default deny incoming   # Deny all unsolicited inbound traffic
sudo ufw default allow outgoing  # Allow all outbound traffic
```
These default rules implement a "default-deny" stance for better security posture.

---
## Current UFW Status

```bash
sudo ufw status verbose
```
## Start and enable the service: 
```
sudo systemctl enable ssh 
sudo systemctl start ssh
``` 

## update default rules to allow SSH port 22
 
```
sudo ufw allow ssh 
# or 
sudo ufw allow 22/tcp 
```


Output:

```vbnet
Status: active

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere
22/tcp (v6)                ALLOW       Anywhere (v6)
```