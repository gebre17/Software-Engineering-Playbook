# JavaScript Interview Questions

Curated questions covering fundamental JS behaviors, closures, scopes, and asynchronous structures.

## 1. What is a Closure in JavaScript?
*   A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the **lexical environment**).
*   In JavaScript, closures are created every time a function is created, at function creation time. It allows an inner function to access the scope of an outer function even after the outer function has finished executing.

```javascript
function makeCounter() {
  let count = 0;
  return function() {
    count++;
    return count;
  };
}

const counter = makeCounter();
console.log(counter()); // 1
console.log(counter()); // 2
```

## 2. Difference between `var`, `let`, and `const`
*   **`var`:** Function-scoped. Can be redeclared and updated. Hoisted with a value of `undefined`.
*   **`let`:** Block-scoped. Cannot be redeclared but can be updated. Hoisted to the Temporal Dead Zone (no default initialization).
*   **`const`:** Block-scoped. Cannot be redeclared or updated (immutable reference). Hoisted to the Temporal Dead Zone.

## 3. What is event delegation?
*   A design pattern of attaching a single event listener to a parent element rather than attaching listeners to multiple individual child nodes.
*   Uses **event bubbling** (events bubble up from the target element to parent nodes in the DOM tree) to capture triggers.

```javascript
const list = document.querySelector('ul');
list.addEventListener('click', (event) => {
  if (event.target.tagName === 'LI') {
    console.log('List item clicked:', event.target.textContent);
  }
});
```
