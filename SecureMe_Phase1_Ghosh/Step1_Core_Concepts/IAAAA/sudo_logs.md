# Configure and Monitor Sudo Logging

## Objective

Ensure accountability by logging all sudo actions.



## Steps

1. **Ensure sudo logging is enabled:**
   Check/Add `/etc/sudoers`:

   ```bash
   Defaults logfile="/var/log/sudo.log"
   ```


3. **Restart rsyslog and test:**

   ```bash
   sudo systemctl restart rsyslog
   sudo -u user sudo ls /
   tail /var/log/auth.log
   ```
## Observation:

sudo.log and auth.log both captured logs for sudo activities.

---