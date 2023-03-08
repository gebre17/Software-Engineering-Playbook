# Python Interview Questions & Concepts

Curated list of technical and conceptual Python questions frequently asked during engineering interviews.

## 1. What is the difference between list and tuple?
*   **List:** Mutable sequence type. Defined with `[]`. Supports in-place modifications (append, extend, remove). Slightly slower due to dynamic resizing overhead.
*   **Tuple:** Immutable sequence type. Defined with `()`. Once created, contents cannot be modified. Faster, consumes less memory, and can be used as dictionary keys (hashable, provided their elements are also hashable).

## 2. Explain Python's GIL (Global Interpreter Lock)
*   **What it is:** A mutex that prevents multiple native threads from executing Python bytecodes at once in CPython.
*   **Why it exists:** Simplifies memory management (guarantees thread-safe reference counting).
*   **How to bypass it:** 
    *   Use the `multiprocessing` module (spawns separate processes with their own GIL).
    *   Use third-party libraries written in C/Rust (like NumPy) which release the GIL during heavy computations.
    *   Use alternative interpreters like Jython or PyPy (some implementations lack GIL).

## 3. How does Memory Management work in Python?
*   **Reference Counting:** Python keeps track of the number of references to each object. When reference count drops to 0, memory is immediately deallocated.
*   **Garbage Collection (GC):** A cyclic garbage collector detects and resolves reference cycles (e.g., Object A references Object B, which references Object A, preventing reference count from ever hitting 0).

## 4. What are mutable default arguments, and why should they be avoided?
When you define a function, default parameters are evaluated *only once* at function definition time, not every time the function is called.

```python
# Bad Pattern
def append_to(element, target=[]):
    target.append(element)
    return target

print(append_to(1)) # [1]
print(append_to(2)) # [1, 2] -- unexpected retention of state!

# Good Pattern
def append_to_good(element, target=None):
    if target is None:
        target = []
    target.append(element)
    return target
```
