# Python Interview Prep

Focused coding challenges, scope patterns, and common algorithmic interview templates in Python.

## Coding Patterns to Know
1.  **Two Pointers:** Great for arrays/strings sorting/matching.
2.  **Sliding Window:** Subarrays, longest substrings.
3.  **Breadth-First Search (BFS) / Depth-First Search (DFS):** Graphs and Trees.

## Quick Python Interview Snippets

### List Comprehension vs. Generator Expression
```python
# List comprehension (creates list in memory)
list_comp = [x * 2 for x in range(1000)]

# Generator expression (lazy evaluation, memory efficient)
gen_expr = (x * 2 for x in range(1000))
```

### Context Managers Boilerplate
```python
class ManagedFile:
    def __init__(self, filename):
        self.filename = filename

    def __enter__(self):
        self.file = open(self.filename, 'r')
        return self.file

    def __exit__(self, exc_type, exc_val, exc_tb):
        if self.file:
            self.file.close()
```
