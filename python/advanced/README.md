# Advanced Python Patterns

Explore advanced language patterns, protocols, and concurrency models in Python.

## 1. Decorators
Functions that modify the behavior of another function without changing its source code.

```python
import functools

def log_calls(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        print(f"Calling {func.__name__} with {args} and {kwargs}")
        result = func(*args, **kwargs)
        print(f"{func.__name__} returned {result}")
        return result
    return wrapper

@log_calls
def add(a, b):
    return a + b
```

## 2. Generators & Iterators
Generators produce values on the fly using `yield`, yielding memory efficiency since they don't load entire sequences in memory.

```python
def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

# Using the generator
for val in fibonacci(5):
    print(val)
```

## 3. Context Managers
Manage resource acquisition and release (e.g., file descriptors, database connections) using the `with` statement.

```python
# Custom Context Manager via generator
from contextlib import contextmanager

@contextmanager
def file_manager(filename, mode):
    f = open(filename, mode)
    try:
        yield f
    finally:
        f.close()
```

## 4. Asyncio (Asynchronous Concurrency)
Asynchronous execution model using the single-threaded event loop.

```python
import asyncio

async def fetch_data(item_id):
    print(f"Fetching data for {item_id}...")
    await asyncio.sleep(1) # Simulates network request
    return {"id": item_id, "data": "value"}

async def main():
    results = await asyncio.gather(
        fetch_data(1),
        fetch_data(2),
        fetch_data(3)
    )
    print(results)

# To run: asyncio.run(main())
```
