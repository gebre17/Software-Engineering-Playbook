# ES6+ Key JavaScript Features

Modern ECMAScript standards introduced powerful syntax enhancements that make JavaScript development cleaner, faster, and more readable.

## 1. Arrow Functions
Provides a shorter syntax and does not bind its own `this` value.
```javascript
const add = (a, b) => a + b;
```

## 2. Destructuring Assignment
Unpack values from arrays or properties from objects into distinct variables.
```javascript
// Object Destructuring
const user = { name: "Alice", age: 25 };
const { name, age } = user;

// Array Destructuring
const colors = ["red", "blue", "green"];
const [primary, secondary] = colors;
```

## 3. Spread & Rest Operators (`...`)
*   **Spread:** Expands elements of an array or object.
*   **Rest:** Condenses multiple elements into a single array parameter.

```javascript
// Spread
const array1 = [1, 2];
const array2 = [...array1, 3, 4]; // [1, 2, 3, 4]

// Rest
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}
```

## 4. ES6 Modules
*   Use `export` to expose functions, classes, or objects from a file.
*   Use `import` to consume them in another file.
