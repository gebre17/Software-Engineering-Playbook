# Python Fundamentals

Python is a high-level, interpreted, dynamically typed programming language known for its readability and clean syntax.

## Basic Data Types
*   **Text Type:** `str` (immutable)
*   **Numeric Types:** `int`, `float`, `complex`
*   **Sequence Types:** `list` (mutable), `tuple` (immutable), `range`
*   **Mapping Type:** `dict` (key-value store, mutable)
*   **Set Types:** `set` (unique items, mutable), `frozenset` (immutable)
*   **Boolean Type:** `bool` (`True` or `False`)

## Control Flow

### If/Else Statements
```python
x = 10
if x > 0:
    print("Positive")
elif x == 0:
    print("Zero")
else:
    print("Negative")
```

### Loops
```python
# For Loop (Iterating over a collection)
for item in ["apple", "banana", "cherry"]:
    print(item)

# While Loop
count = 0
while count < 3:
    print(count)
    count += 1
```

## Functions & Argument Types
Functions are defined using the `def` keyword.
*   **Positional Arguments:** Matched by order.
*   **Keyword Arguments:** Specified by name.
*   **Default Parameters:** Fallback values if arguments are omitted.
*   **Arbitrary Arguments (`*args`, `**kwargs`):** Handling arbitrary numbers of positional or keyword parameters.

```python
def greet(name, greeting="Hello", *hobbies, **metadata):
    print(f"{greeting}, {name}!")
    print(f"Hobbies: {hobbies}")
    print(f"Metadata: {metadata}")
```
