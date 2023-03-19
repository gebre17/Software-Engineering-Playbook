# React Interview Prep

Key architectural, performance, and API concepts in React interviews.

## Core Questions

### 1. What is the Virtual DOM and how does React reconciliation work?
*   **Virtual DOM:** A lightweight, in-memory representation of the real DOM.
*   **Reconciliation:** The process by which React updates the real DOM.
    1.  When state changes, React generates a new Virtual DOM tree.
    2.  React compares the new tree with the old tree (Diffing Algorithm).
    3.  React calculates the minimal set of changes required to update the real DOM and applies them.

### 2. What are the rules of keys in React lists?
*   Keys must be **stable**, **predictable**, and **unique** among sibling elements.
*   *Why indexes are bad keys:* If elements are reordered, inserted, or deleted, index changes cause unnecessary re-renders or state mismatches.

### 3. How do you optimize React rendering?
*   Use `useMemo` and `useCallback` to cache computations and callbacks.
*   Use `React.memo` to prevent child re-renders.
*   Split large components and load them lazily using `React.lazy`.
