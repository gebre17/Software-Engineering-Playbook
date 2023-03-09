# JavaScript Async/Await & Concurrency

JavaScript is single-threaded and executes asynchronous code using the Event Loop (Call Stack, Web APIs, Callback Queue, Microtask Queue).

## Promises
An object representing the eventual completion (or failure) of an asynchronous operation.
*   *States:* `pending`, `fulfilled`, `rejected`.

```javascript
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Success!"), 1000);
});

myPromise.then(result => console.log(result)).catch(err => console.error(err));
```

## Async/Await
A syntactical sugar wrapper over Promises, enabling clean, synchronous-looking asynchronous flows.

```javascript
async function fetchData() {
  try {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Fetch failed:", error);
  }
}
```

## Parallel Execution (`Promise.all`)
Executing multiple independent promises in parallel rather than sequentially.

```javascript
async function fetchAll() {
  const [res1, res2] = await Promise.all([
    fetch("https://api.example.com/users"),
    fetch("https://api.example.com/posts")
  ]);
  return [await res1.json(), await res2.json()];
}
```
