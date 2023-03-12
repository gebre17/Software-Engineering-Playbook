# PostgreSQL Reference

PostgreSQL is a powerful, open-source object-relational database system known for its reliability, feature robustness, and performance.

## Indexing
Indexes are used to speed up the retrieval of data from the database.
*   **B-Tree (Default):** Great for comparison operators (`=`, `<`, `<=`, `>`, `>=`) and sorting.
*   **Hash:** Fast for exact equality matches (`=`).
*   **GIN (Generalized Inverted Index):** Ideal for arrays and full-text search columns.

```sql
CREATE INDEX idx_users_email ON users(email);
```

## Analyzing Query Performance
Using `EXPLAIN ANALYZE` to execute a query and output the database execution plan, costs, and execution time statistics.

```sql
EXPLAIN ANALYZE SELECT * FROM users WHERE email = 'test@example.com';
```

## Common Table Expressions (CTEs) & Window Functions

### CTE
Allows writing modular, readable query blocks.
```sql
WITH regional_sales AS (
    SELECT region, SUM(amount) AS total_sales
    FROM orders
    GROUP BY region
)
SELECT region, total_sales FROM regional_sales WHERE total_sales > 10000;
```

### Window Functions
Perform a calculation across a set of table rows that are related to the current row.
```sql
SELECT employee_name, department, salary,
       RANK() OVER (PARTITION BY department ORDER BY salary DESC) as salary_rank
FROM employees;
```
