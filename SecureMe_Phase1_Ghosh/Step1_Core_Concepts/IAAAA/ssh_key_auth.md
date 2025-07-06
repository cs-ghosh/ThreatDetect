# Task: SSH Key-based Authentication Setup

## Objective

Enhance secure remote access by using public-private key authentication instead of password-based login.

## Tools Used

* `ssh-keygen`, `ssh-copy-id`, `sshd_config`

## Steps followed

1. **Generate SSH key pair:**

   ```bash
   ssh-keygen -b 4096
   ```

2. **Test ssh connection with target user's password**

   ```bash
   ssh non-root-user@<server_ip>
   ```

3. **Disable password authentication(optional) :**
   Edit `/etc/ssh/sshd_config`:

   ```
   PermitRootLogin no
   ```

   Restart SSH service:

   ```bash
   sudo systemctl restart ssh
   ```

4. **exit and copy public key to target system:**

   ```bash
   ssh-copy-id user@<server_ip>
   ```

5. **Test ssh connection again for passwordless login**. 

   ```bash
   ssh non-root-user@<server_ip>
   #Enter ssh key passphrase only, not user's password
   ```

## Observation:
User logged in successfully with ssh connection without entering user's password.