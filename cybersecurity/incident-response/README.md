# Incident Response & Threat Modeling

An incident response framework to detect, contain, and recover from security breaches.

## Incident Response Steps

```mermaid
graph LR
    Prep[Preparation] --> Detect[Detection]
    Detect --> Contain[Containment]
    Contain --> Eradicate[Eradication]
    Eradicate --> Recover[Recovery]
    Recover --> Post[Post-Incident Review]
```

1.  **Preparation:** Build and train incident response teams, establish communication paths, set up audit logging.
2.  **Detection & Analysis:** Identifying anomalies via metrics/log monitors (e.g., unexpected spikes in SSH login attempts, large data egress).
3.  **Containment:** Isolating affected servers (e.g., changing firewall rules, terminating sessions) to prevent lateral movement.
4.  **Eradication:** Removing malware, revoking compromised access keys, restoring systems from clean backups.
5.  **Recovery:** Bringing clean systems back into production.
6.  **Post-Incident Review (Post-Mortem):** Reviewing actions taken and updating the plan to prevent identical exploits.

## Threat Modeling Frameworks
*   **STRIDE:**
    *   **S**poofing identity
    *   **T**ampering with data
    *   **R**epudiation
    *   **I**nformation disclosure
    *   **D**enial of service
    *   **E**levation of privilege
