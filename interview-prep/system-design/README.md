# System Design Interview Prep

A guide to structuring and executing system design interviews.

## Step-by-Step Interview Framework

```
  Step 1: Clarify Requirements (Functional & Non-functional)
                       │
                       ▼
  Step 2: Core Estimations (Throughput, Storage size, Network capacity)
                       │
                       ▼
  Step 3: High-Level Architecture (Core API routes, System diagram)
                       │
                       ▼
  Step 4: Detailed Component Design (Data models, DB choice, Scalability)
                       │
                       ▼
  Step 5: Identify Bottlenecks (Single points of failure, scaling, caching)
```

## Key Concept Checklists

### Database Selection
*   **SQL (Relational):** Best for structured data requiring strong consistency, ACID compliance, complex JOINs (e.g., banking/billing).
*   **NoSQL (Non-Relational):**
    *   *Key-Value:* Redis (caching, fast lookup).
    *   *Document:* MongoDB (dynamic schemas, nested JSON structures).
    *   *Columnar:* Cassandra (huge scale, high write throughput, analytics).

### Scalability Checklist
- [ ] Load balancers at entry points.
- [ ] CDN for static asset delivery.
- [ ] Read replicas to distribute database reads.
- [ ] Redis caching layer.
- [ ] Message queues (Kafka) to process tasks asynchronously.
