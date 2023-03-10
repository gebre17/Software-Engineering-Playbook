# React Hooks

React Hooks allow functional components to manage state, lifecycle effects, and other React features without writing class components.

## Core Hooks

### 1. `useState`
Declares state variables in a functional component.
```jsx
const [count, setCount] = useState(0);
```

### 2. `useEffect`
Performs side effects (data fetching, DOM updates, event listeners) in functional components.
```jsx
useEffect(() => {
  console.log("Component mounted or state changed");
  
  return () => {
    console.log("Cleanup phase");
  };
}, [dependencies]);
```

### 3. `useRef`
Persists a mutable value across renders without triggering a re-render. Primarily used to reference DOM elements directly.
```jsx
const inputRef = useRef(null);
// Accessing DOM element: inputRef.current.focus()
```

## Rules of Hooks
*   Only call Hooks at the top level (not inside loops, conditions, or nested functions).
*   Only call Hooks from React functional components or Custom Hooks.
