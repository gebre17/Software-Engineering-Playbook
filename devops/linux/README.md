# Linux Commands & Concepts

Linux is the foundational operating system for deploying and managing server infrastructure.

## Essential CLI Commands
*   **Navigation & Files:** `ls`, `cd`, `pwd`, `cp`, `mv`, `rm`, `mkdir`, `touch`.
*   **File Viewing & Searching:** `cat`, `less`, `grep`, `find`, `tail -f` (follow logs).
*   **System Diagnostics:** `df -h` (disk space), `free -m` (memory usage), `top` or `htop` (processes).
*   **Network Diagnostics:** `ping`, `curl`, `wget`, `netstat` or `ss -tulpn` (active listening ports).

## Systemd & Service Management
Standard system daemon for managing system services and processes.

```bash
# Start a service
sudo systemctl start nginx

# Enable a service to run on boot
sudo systemctl enable nginx

# Inspect logs for a specific service
journalctl -u nginx.service -n 50 --no-pager
```

## Permissions Model
Linux files have three permissions scopes: Owner (User), Group, and Others.
Permissions types: Read (`r` = 4), Write (`w` = 2), Execute (`x` = 1).

```bash
# Change permissions to read/write/execute for owner, read-only for group/others (744)
chmod 744 script.sh

# Change owner
chown root:root script.sh
```
