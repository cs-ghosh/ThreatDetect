# Linux Log File Exploration

## Objective

Explore and analyze essential Linux log files under `/var/log` to identify system events, authentication attempts, service issues.

---

## Explored Log Files

| Log File              | Purpose                                           |
|-----------------------|---------------------------------------------------|
| `/var/log/syslog`     | General system events and messages               |
| `/var/log/auth.log`   | User login attempts and sudo authentication logs |
| `/var/log/dpkg.log`   | Package installation, upgrade, removal history    |
| `/var/log/kern.log`   | Kernel-level messages                            |
| `journalctl`          | Systemd logs including service status and errors |

---

## Sample commands used to identify failed login, service errors
 
```bash
tail -n 20 /var/log/auth.log 
sudo journalctl -xe | head -n 20 

grep "Failed password" /var/log/auth.log
grep -i error /var/log/syslog | tail -n 10

```

- Failed password error (auth.log)
    ```
    Jul  6 13:55:12 ubuntu sshd[12345]: Failed password for user1 from 192.168.1.15 port 51874 ssh2
    ```
    This log shows an SSH login attempt where the user user1 entered an incorrect password. It indicates a potential unauthorized access attempt or user error, and should be monitored for repeated failures from the same IP

- OpenSearch Dashboard SSL Error(syslog)
    ```
    ERR_SSL_SSLV3_ALERT_CERTIFICATE_UNKNOWN
    ```
    This indicates OpenSearch Dashboard failed to load securely due to an unrecognized or untrusted SSL certificate. This can block access and indicates a misconfigured or self-signed certificate.