# IP Multimedia Subsystem (IMS)

IP Multimedia Subsystem (IMS) is a standardized architectural framework for delivering IP multimedia services (such as voice, video calling, and rich messaging) over IP networks.

## Core Protocols
*   **SIP (Session Initiation Protocol):** Used to establish, modify, and terminate multimedia sessions (calls).
*   **SDP (Session Description Protocol):** Embedded inside SIP payloads to negotiate media parameters (codecs, IP addresses, port numbers).
*   **RTP / RTCP (Real-time Transport Protocol):** Transports actual audio/video payloads in real time.

## IMS Core Elements (CSCF)
The Call Session Control Function (CSCF) acts as the central SIP server routing node in IMS.

```
       +---------------------------------------------+
       |                  IMS Core                   |
       |                                             |
SIP    |  +------------+   +------------+   +-----+  |
-----> |  |   P-CSCF   |-->|   S-CSCF   |-->| HSS |  |
       |  | (Access)   |   | (Registrar)|   +-----+  |
       |  +------------+   +------------+      ^     |
       |        ^                ^             |     |
       |        |                |             |     |
       |        v                v             |     |
       |  +------------+         +-------------+     |
       |  |   I-CSCF   |-----------------------------+  |
       |  | (Interrog.)|                             |
       |  +------------+                             |
       +---------------------------------------------+
```

### 1. P-CSCF (Proxy CSCF)
*   The first point of contact for the UE.
*   Acts as a SIP proxy, securing the user connection, and performing compression/security checks.

### 2. I-CSCF (Interrogating CSCF)
*   The entry point from external networks.
*   Queries the HSS to find the correct S-CSCF assigned to a user during registration.

### 3. S-CSCF (Serving CSCF)
*   The main brain. Acts as a SIP registrar and performs session control, authenticating the user and executing routing decisions.
