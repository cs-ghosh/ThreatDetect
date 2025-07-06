
# Analyze Linux Log Files

## Objective

Establish an audit trail by reviewing authentication and authorization events from Linux log files.

## Key File Locations
`/etc/rsyslog.conf`, `/var/log/auth.log`

## Analysis Steps

1. **View authentication logs:**

   ```bash
   sudo cat /var/log/auth.log
   ```

2. **Search for login attempts:**

   ```bash
   grep "sshd" /var/log/auth.log | grep "Accepted"
   ```

3. **Search for sudo activity:**

   ```bash
   grep "sudo" /var/log/auth.log
   ```

4. **Review failed logins or suspicious activity:**

   ```bash
   grep "Failed password" /var/log/auth.log
   ```