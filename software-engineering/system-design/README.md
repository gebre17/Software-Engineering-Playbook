# System Design

System design is the process of defining the architecture, modules, interfaces, and data flow for a system to satisfy specified requirements.

## Key Concepts

### 1. Scalability
*   **Vertical Scaling (Scale Up):** Adding more power (CPU, RAM) to an existing machine.
*   **Horizontal Scaling (Scale Out):** Adding more machines to the resource pool.

### 2. High Availability & Fault Tolerance
*   **Redundancy:** Duplicating critical components so if one fails, others take over.
*   **SLA (Service Level Agreement):** The percentage of time a service is up (e.g., 99.99% "four nines").

### 3. Load Balancing
Distributes incoming network traffic across a group of backend servers.
*   *Algorithms:* Round Robin, Least Connections, IP Hash.

### 4. Caching Strategies
*   **Read-Through:** Application queries cache. If miss, cache queries DB, updates self, and returns to app.
*   **Write-Through:** Data written to cache and DB simultaneously.
*   **Write-Back (Write-Behind):** Data written to cache immediately, and written to DB asynchronously.

### 5. Database Partitioning & Replication
*   **Replication:** Copying data across multiple DB instances (Primary-Replica).
*   **Sharding:** Horizontal partitioning of databases by splitting rows across multiple DB instances based on a shard key.
