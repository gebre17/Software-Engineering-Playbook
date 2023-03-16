# Routing & Subnets

Routing is the process of selecting paths in a network along which to send network traffic.

## Subnetting & CIDR (Classless Inter-Domain Routing)
IP addresses are split into a network portion and a host portion using a subnet mask.
*   *Example:* `192.168.1.0/24`
    *   Subnet Mask: `255.255.255.0`
    *   Total IPs: 256 ($2^{32-24}$)
    *   Usable Host IPs: 254 (Network Address `192.168.1.0` and Broadcast Address `192.168.1.255` are reserved).

## Core Routing Protocols

### 1. BGP (Border Gateway Protocol)
*   The protocol that makes the internet work.
*   Path-vector routing protocol used to exchange routing information between different Autonomous Systems (AS).

### 2. OSPF (Open Shortest Path First)
*   Link-state routing protocol used within a single Autonomous System (interior routing).
*   Uses Dijkstra's algorithm to compute the shortest path tree.

## NAT (Network Address Translation)
Translates private, non-routable IP addresses (e.g., `10.x.x.x`, `192.168.x.x`) inside a local area network to a single public IP address to communicate with external hosts.
*   **PAT (Port Address Translation):** Maps multiple private hosts to a single public IP by changing the source port numbers.
