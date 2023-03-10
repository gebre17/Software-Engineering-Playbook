# React State Management

Managing data flow and synchronization across React component hierarchies.

## State Options

### 1. Local State (`useState` / `useReducer`)
Best for simple, isolated component state (e.g., toggle menus, local inputs).

### 2. Context API
Built-in solution to share state globally without manually passing props through intermediate components ("prop drilling").
*   *Caveat:* Any state change in a Provider triggers re-renders on all descendants. Avoid for highly dynamic/frequently updated state.

### 3. Redux Toolkit (RTK)
Standard library for global state management using a centralized, predictable state container (actions, reducers, store).
*   *Use-case:* Large, complex enterprise applications with many asynchronous state interactions.

### 4. Zustand
A lightweight, modern, hook-based alternative to Redux. Highly performant and simple to set up.

```javascript
import { create } from 'zustand'

const useStore = create((set) => ({
  bears: 0,
  increasePopulation: () => set((state) => ({ bears: state.bears + 1 })),
  removeAllBears: () => set({ bears: 0 }),
}))
```
