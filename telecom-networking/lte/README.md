# Long Term Evolution (LTE) Network Architecture

LTE (4G) is a cellular standard designed to provide high-speed data access for mobile phones and data terminals.

## System Architecture Evolution (SAE)
LTE features a simplified, flat, IP-only network architecture split into two main sections:

```
+---------------+     LTE Uu     +---------------+     S1-MME     +---------------+
|               | <------------> |    eNodeB     | <------------> |      MME      |
|  User Equip.  |                | (Base Station)|                | (Control Plane|
|     (UE)      |                +---------------+                +---------------+
|               |                      | S1-U                            | S6a
+---------------+                      v                                 v
                                 +---------------+     S5/S8      +---------------+
                                 |     S-GW      | <------------> |     P-GW      |
                                 | (User Plane)  |                | (Packet Gate) |
                                 +---------------+                +---------------+
```

### 1. E-UTRAN (Evolved Universal Terrestrial Radio Access Network)
*   **UE (User Equipment):** The mobile phone/device.
*   **eNodeB (Evolved Node B):** The physical base station transceiver. Controls radio resources and performs encryption/compression.

### 2. EPC (Evolved Packet Core)
*   **MME (Mobility Management Entity):** The primary control node. Performs user authentication, mobility tracking (paging/handover), and session establishment.
*   **S-GW (Serving Gateway):** Routes user data packets and acts as the local mobility anchor when the UE moves between eNodeBs.
*   **P-GW (PDN Gateway):** The interface between the EPC and external packet networks (e.g., Internet). Assigns IP addresses to UEs.
*   **HSS (Home Subscriber Server):** Master database containing user profile and subscription info.
