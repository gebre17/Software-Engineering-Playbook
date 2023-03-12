# Redis Reference

Redis is an open-source, in-memory data structure store used as a database, cache, message broker, and streaming engine.

## Core Data Types
*   **Strings:** Standard key-value pairs (text or binary data up to 512MB).
*   **Lists:** Ordered collections of strings, sorted by insertion order.
*   **Sets:** Unordered collections of unique strings.
*   **Sorted Sets (ZSET):** Sets where every member is associated with a score, ordered by score.
*   **Hashes:** Maps between string fields and string values (ideal for representing objects).

## Caching Strategies

*   **TTL (Time To Live):** Setting expiration times on keys to automatically purge stale data.
*   **Eviction Policies:**
    *   `noeviction`: Returns errors when memory limit is reached.
    *   `allkeys-lru`: Evicts least recently used keys first.
    *   `volatile-lru`: Evicts least recently used keys with an expire set first.

## Commands Reference
```bash
# Set key-value with 60-second TTL
SET mykey "Hello" EX 60

# Retrieve key
GET mykey

# Add item to list
LPUSH mylist "item1"

# Increment integer key
INCR counter
```
