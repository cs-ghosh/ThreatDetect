# Linux Command Practice 


| **Category**    | **Command**         | **What it Does**                                     | **Sample Output**                                      |
|----------------|---------------------|------------------------------------------------------|--------------------------------------------------------|
| Navigation     | `pwd`               | Prints current working directory                     | `/home/user1`                                         |
|                | `ls -l`             | Lists files with permissions, owner, size, time      | `-rw-r--r-- 1 user user 4096 Jul 2 11:30 file.txt`     |
|                | `cd /var/log`       | Changes to specified directory                       | *(no output on success)*                               |
|                | `tree`              | Displays directory tree structure                    | `. ├── file1.txt └── folder1 └── file2.txt`            |
| File Ops       | `touch file.txt`    | Creates a new empty file                             | *(no output on success)*                               |
|                | `mkdir reports`     | Creates a new directory                              | *(no output on success)*                               |
|                | `rm file.txt`       | Deletes a file                                       | *(no output on success)*                               |
|                | `cp file1 backup/`  | Copies file1 to backup directory                     | *(no output on success)*                               |
|                | `mv a.txt b.txt`    | Renames or moves a file                              | *(no output on success)*                               |
| Permissions    | `chmod 644 file`    | Sets file permissions to rw-r--r--                   | *(no output on success)*                               |
|                | `chown root file`   | Changes file owner to root                           | *(no output on success)*                               |
|                | `ls -la`            | Lists all files (including hidden) in long format    | `-rw-r--r-- 1 user user 0 Jul 2 11:30 .bashrc`         |
| Users          | `whoami`            | Prints current logged-in username                    | `user1`                                               |
|                | `id`                | Shows UID, GID, and group memberships                | `uid=1001(user1) gid=1001 groups=1001,27(sudo)`       |
|                | `adduser testuser`  | Adds a new user to the system                        | `Adding user 'testuser' ...`                           |
|                | `passwd testuser`   | Sets or changes user password                        | `Enter new UNIX password:`                             |
| Networking     | `ifconfig`          | Displays network interfaces (legacy)                 | `inet 192.168.1.10 netmask 255.255.255.0`              |
|                | `ip a`              | Shows IP and interface details                       | `inet 192.168.1.10/24 brd 192.168.1.255 ...`           |
|                | `ping google.com`   | Tests network connectivity                           | `64 bytes from google.com: icmp_seq=1 ttl=117 ...`     |
|                | `netstat -tuln`     | Lists listening ports                                | `tcp 0 0 0.0.0.0:22 0.0.0.0:* LISTEN`                  |
|                | `ss -tuln`          | Shows open sockets and listening ports               | `LISTEN 0 128 *:22 *:*`                                |
| System         | `top`               | Displays live process and resource usage             | `PID USER PR NI VIRT RES SHR S CPU% MEM% TIME+ COMMAND`|
|                | `uptime`            | Shows system uptime and load average                 | `11:10:01 up 1 day, 3:10, load average: 0.10, 0.12...` |
|                | `df -h`             | Shows disk space usage in human-readable form        | `/dev/sda1 30G 12G 16G 43% /`                          |
|                | `uname -a`          | Prints kernel name, version, and system architecture | `Linux host 5.15.0-91-generic x86_64 GNU/Linux`        |
|                | `shutdown -h now`   | Shuts down the system immediately                    | Broadcast message: System is going down for halt now   |
|----------------|---------------------|------------------------------------------------------|--------------------------------------------------------|
