# MySQL Reference

A guide to engines, transactions, and optimizations in MySQL.

## Storage Engines

### 1. InnoDB (Default)
*   Supports transactions (ACID compliant).
*   Supports row-level locking.
*   Supports foreign keys.
*   *Use-case:* Enterprise standard for transactional databases.

### 2. MyISAM
*   No transaction support.
*   Table-level locking only.
*   No foreign keys.
*   *Use-case:* Read-heavy operations that do not require transactions (largely deprecated/replaced by InnoDB in modern setups).

## Table Partitioning
Splitting a single table physically across directories while keeping it logical to speed up queries by scanning only relevant partitions.

```sql
CREATE TABLE sales (
    id INT,
    sale_date DATE
)
PARTITION BY RANGE (YEAR(sale_date)) (
    PARTITION p0 VALUES LESS THAN (2025),
    PARTITION p1 VALUES LESS THAN (2026),
    PARTITION p2 VALUES LESS THAN MAXVALUE
);
```
