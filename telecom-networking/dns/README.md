# Domain Name System (DNS)

The Domain Name System (DNS) translates human-readable domain names (e.g., `example.com`) into machine-readable IP addresses (e.g., `93.184.216.34`).

## Resolution Flow
1.  **Browser Cache:** Browser checks if it has the IP cached.
2.  **OS Cache / Resolver:** OS queries the local resolver (e.g., local ISP or public DNS like `8.8.8.8`).
3.  **Root Nameserver:** Resolver queries Root Nameserver (`.`) to find Top-Level Domain (TLD) server.
4.  **TLD Nameserver:** Resolver queries TLD Nameserver (e.g., `.com`) to locate Authoritative Nameserver.
5.  **Authoritative Nameserver:** Resolver queries Authoritative Nameserver for the zone, which returns the actual IP address mapping.
6.  **Local Cache:** Resolver caches the IP and returns it to the client.

## Core DNS Record Types

*   **A Record:** Maps a domain name to an IPv4 address.
*   **AAAA Record:** Maps a domain name to an IPv6 address.
*   **CNAME (Canonical Name) Record:** Alias of one domain name to another (e.g., `www.example.com` redirects to `example.com`).
*   **MX (Mail Exchanger) Record:** Specifies the mail servers responsible for receiving email for a domain.
*   **TXT Record:** Allows domain owners to store text notes (commonly used for security checks like SPF, DKIM, and site ownership verifications).
*   **NS (Name Server) Record:** Defines which nameservers are authoritative for a domain.
