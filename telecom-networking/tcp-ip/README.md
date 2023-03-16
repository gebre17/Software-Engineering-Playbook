# TCP/IP & Networking Fundamentals

The internet protocol suite (TCP/IP) represents the conceptual model and set of communications protocols used on the Internet.

## The 4-Layer TCP/IP Model vs. 7-Layer OSI Model

| Layer | OSI Model Layer Name | TCP/IP Model Layer Name | Example Protocols |
|---|---|---|---|
| 7 | Application | Application | HTTP, DNS, SIP, SMTP |
| 6 | Presentation | Application | SSL/TLS |
| 5 | Session | Application | SOCKS, NetBIOS |
| 4 | Transport | Transport | TCP, UDP |
| 3 | Network | Internet | IPv4, IPv6, ICMP, IPsec |
| 2 | Data Link | Network Access | Ethernet, Wi-Fi (802.11) |
| 1 | Physical | Network Access | Physical copper cable, fiber |

## The TCP Three-Way Handshake
Used to establish a reliable, stateful connection between client and server.

```
Client                                  Server
  |                                       |
  | -------- SYN (Seq=x) ---------------> |  (Client requests connection)
  |                                       |
  | <------- SYN-ACK (Seq=y, Ack=x+1) --- |  (Server acknowledges and accepts)
  |                                       |
  | -------- ACK (Ack=y+1) -------------> |  (Client acknowledges, connection ESTABLISHED)
  v                                       v
```
*   **SYN:** Synchronize sequence numbers.
*   **ACK:** Acknowledge receipts.
