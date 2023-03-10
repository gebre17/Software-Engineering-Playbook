# React Optimization

Optimizing web application performance, bundle size, and rendering speed.

## Core Optimization Concepts

### 1. Reducing Unnecessary Re-renders
*   **`useMemo`:** Caches the result of a calculation between re-renders to prevent heavy computation overhead.
*   **`useCallback`:** Caches the function definition itself to prevent child components from re-rendering due to changing prop references.
*   **`React.memo`:** Higher-order component that skips re-rendering a component if its props haven't changed.

### 2. Code Splitting & Lazy Loading
Splitting large client-side bundles into dynamic chunks loaded only when a specific route or element is accessed.

```jsx
import React, { lazy, Suspense } from 'react';

const HeavyComponent = lazy(() => import('./HeavyComponent'));

function MyComponent() {
  return (
    <Suspense fallback={<div>Loading component chunk...</div>}>
      <HeavyComponent />
    </Suspense>
  );
}
```

### 3. List Virtualization
Only rendering elements in a list that are currently visible within the user's viewport (using libraries like `react-window` or `react-virtualized`), preventing rendering overhead for lists of 1000+ elements.
