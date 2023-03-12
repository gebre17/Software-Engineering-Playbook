# Database Optimization Patterns

Optimizing performance and stability across database layers.

## 1. Connection Pooling
Instead of creating and destroying database connections for every request (which incurs huge TCP/handshake overhead), connection pools maintain a cache of active connections.
*   *Tools:* PGpool-II, PgBouncer (standard for PostgreSQL).

## 2. Query Optimization Checklist
- [ ] **Avoid `SELECT *`:** Only retrieve columns that are actually needed to minimize memory and networking costs.
- [ ] **Create Indexes:** Add indexes for columns in `WHERE`, `JOIN`, `ORDER BY`, and `GROUP BY` statements.
- [ ] **Avoid Subqueries:** Replace nested subqueries with efficient `JOIN` operations.
- [ ] **Use Database Views/Materialized Views:** Precompute complex queries and cache results.

## 3. Database Replication & Partitioning
*   **Read-Write Splitting:** Route write operations to a primary database instance, and route read queries across multiple read replicas.
*   **Vertical Partitioning:** Split a table's columns across multiple tables (e.g., placing rarely accessed columns in a metadata table).
