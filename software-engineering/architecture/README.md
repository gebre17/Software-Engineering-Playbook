# Software Architecture

Software architecture represents the high-level structures of a software system, the relationships among them, and the principles guiding their design and evolution.

## Common Architecture Patterns

### 1. Monolith
*   All logic, static assets, and configurations are packaged and deployed in a single unit.
*   *Pros:* Simpler deployment, debugging, and testing early on.
*   *Cons:* Scaling bottlenecks, high coupling, slower build times for large codebases.

### 2. Microservices
*   An application is decomposed into small, independent, self-contained services that communicate via lightweight protocols (REST API, gRPC, Message Queues).
*   *Pros:* Technology diversity, independent scalability, localized deployment.
*   *Cons:* Complex orchestration, data consistency issues (distributed transactions), networking latency.

### 3. Hexagonal Architecture (Ports and Adapters)
*   Separates core business logic from external systems (database, web UI, external APIs) using interface adapters.
*   *Ports:* Interfaces defining how external adapters communicate with core business logic.
*   *Adapters:* Concretions of those interfaces (e.g., a SQL Database adapter implementing a Repository port).

### 4. Event-Driven Architecture (EDA)
*   Services communicate by producing and consuming events asynchronously via a message broker (e.g., RabbitMQ, Apache Kafka).
*   *Benefits:* Loose coupling, high scalability, improved resilience.
