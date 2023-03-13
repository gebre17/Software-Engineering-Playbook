# Debugging Guide

Debugging is the process of identifying, analyzing, and resolving bugs or defects in software.

## The Debugging Process
1.  **Reproduce:** Create a stable, isolated test case that demonstrates the bug.
2.  **Locate:** Trace the code path using logs, stack traces, and debuggers.
3.  **Analyze:** Determine the root cause of the behavior.
4.  **Fix:** Implement and verify a fix without introducing side effects.
5.  **Reflect:** Add tests to prevent regressions.

## Tools & Approaches

### 1. Interactive Debugging (pdb / ipdb / IDE Debuggers)
Using breakpoints to pause execution and inspect variables.
```python
# In python, drop into debugger session:
import pdb; pdb.set_trace()
# Or in modern Python:
breakpoint()
```

### 2. Log Analysis
Ensuring correct logging levels are used:
*   `DEBUG`: Low-level tracing, variable states.
*   `INFO`: High-level flow verification.
*   `WARNING`: Unexpected conditions that aren't errors.
*   `ERROR`: Failure of a specific operation.
*   `CRITICAL`: System-wide failure (e.g., DB connection down).

### 3. Profiling & Performance Analysis
Identifying bottlenecks in execution CPU/Memory.
*   *Python:* `cProfile`, `line_profiler`, `memory_profiler`.
*   *Linux/OS:* `top`, `htop`, `strace`, `lsof`.
