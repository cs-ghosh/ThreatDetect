# Task: Linux User Creation and Permission Management

## Objective

Ensure proper identity and authorization controls by creating and managing Linux users and assigning appropriate permissions.

## Steps

1. **Create a new user:**

   ```bash
   sudo useradd -m -s /bin/bash user1
   sudo passwd user1
   sudo useradd -m -s /bin/bash user2
   sudo passwd user2
   ```

2. **Add user1 to sudo group:**

   ```bash
   sudo usermod -aG sudo user1
   ```

3. **Create new group and assign user1 to a new group:**

   ```bash
   sudo groupadd security
   sudo usermod -aG security user1
   ```

4. **Change ownership and permissions of directory:**

   ```bash
   sudo mkdir /opt/security_logs
   sudo chown user1:security /opt/security_logs
   sudo chmod 750 /opt/security_logs
   ```

---
## Observation:

- user1 was part of sudo and security group with access to sucrity_logs.
- user2 has no permission to access security_logs.