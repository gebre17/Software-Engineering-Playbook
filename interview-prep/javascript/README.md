# JavaScript Interview Prep

Advanced coding, closures, prototyping, and async interview questions.

## Core Questions

### 1. Explain the difference between `==` and `===`
*   `==` (Loose Equality): Performs type coercion before comparing values.
*   `===` (Strict Equality): Compares both value and type without coercion.

```javascript
5 == '5'  // true
5 === '5' // false
```

### 2. How does the JavaScript Event Loop work?
1.  **Call Stack:** Single-threaded execution of synchronous code.
2.  **Web APIs:** Browser handling of async events (timeouts, DOM clicks, network requests).
3.  **Callback (Task) Queue:** Queue of actions from Web APIs waiting to run.
4.  **Microtask Queue:** High-priority queue (e.g., Promise callbacks, `process.nextTick`).
5.  **Event Loop:** Continuous process checking if Call Stack is empty. If empty, it pushes events from Microtask Queue, then Callback Queue.

### 3. What is hoisting?
JavaScript moves declarations of variables, functions, and classes to the top of their scope before code execution.
*   Functions are hoisted with their definitions.
*   `var` is hoisted with a value of `undefined`.
*   `let`/`const` are hoisted but not initialized (remain in the Temporal Dead Zone).
