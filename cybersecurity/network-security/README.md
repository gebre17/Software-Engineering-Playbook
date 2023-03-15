# Network Security Reference

Best practices for securing server network layers and communication channels.

## 1. Firewalls & Ports
Strictly limit the network footprint of hosts.
*   **ufw (Uncomplicated Firewall) / iptables:** Set up default drop policies for incoming connections.
*   **Rules Checklist:**
    *   Port `80`/`443` (HTTP/HTTPS) -> Open to public.
    *   Port `22` (SSH) -> Restrict to specific trusted IP ranges.
    *   Port `5432` / `3306` (PostgreSQL / MySQL) -> Keep closed to public. Only open local loopback (`127.0.0.1`) or private VPC subnet.

## 2. SSH Hardening (`/etc/ssh/sshd_config`)
*   Disable password-based authentication (`PasswordAuthentication no`). Rely strictly on SSH keys (RSA 4096-bit or Ed25519).
*   Disable root logins (`PermitRootLogin no`).
*   Change the default SSH port (e.g., from `22` to a high custom port) to evade automated scanner bots.

## 3. SSL/TLS Handshake Security
Always utilize TLS 1.2 or TLS 1.3. Disable legacy, vulnerable versions (SSL v2/v3, TLS 1.0/1.1) to prevent decryption attacks.
