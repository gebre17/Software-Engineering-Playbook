# Voice over LTE (VoLTE)

Voice over LTE (VoLTE) delivers voice calls over 4G LTE packet networks instead of traditional circuit-switched fallback (CSFB) 2G/3G networks, leveraging IMS.

## Key Benefits
*   **High Definition (HD) Voice:** Uses advanced audio codecs (e.g., AMR-WB, EVS) spanning a broader frequency range.
*   **Faster Call Setup Time:** Call connection established in ~1-2 seconds compared to 5-8 seconds for 2G/3G CSFB.
*   **Simultaneous Voice & LTE Data:** Users can browse the internet at 4G speeds while actively on a voice call.

## Quality of Service (QoS) & QCI
LTE network assigns different Quality of Service Class Identifiers (QCI) to control latency and packet loss depending on traffic type.

| QCI | Resource Type | Delay Budget | Packet Error Loss | Example Services |
|---|---|---|---|---|
| **1** | Guaranteed Bit Rate (GBR) | 100 ms | $10^{-2}$ | **Conversational Voice (VoLTE Audio)** |
| **2** | GBR | 150 ms | $10^{-3}$ | Conversational Video (Video Call) |
| **5** | Non-GBR | 100 ms | $10^{-6}$ | **IMS Signaling (SIP Register/Invite)** |
| **9** | Non-GBR | 300 ms | $10^{-6}$ | Default Internet (Web Browsing, email) |

## VoLTE Call Flow (High Level)
1.  **SIP Registration:** UE registers with the IMS core via the P-CSCF over QCI 5 (default bearer).
2.  **SIP INVITE:** Initiating a call sends a SIP INVITE from the calling party to S-CSCF.
3.  **Dedicated Bearer Activation:** Core network sets up a QCI 1 Dedicated Bearer (GBR) for voice media traffic.
4.  **RTP Voice Stream:** Actual audio packets traverse the network via RTP over the QCI 1 bearer.
5.  **SIP BYE:** Ending the call sends a SIP BYE, releasing the QCI 1 bearer.
