# React Routing

Routing architectures for single-page applications (SPAs) and server-rendered (SSR) React applications.

## 1. Client-Side Routing (React Router v6)
Routes are matched entirely in the client-side JavaScript bundle.

```jsx
import { BrowserRouter, Routes, Route } from "react-router-dom";

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/users/:id" element={<UserDetail />} />
      </Routes>
    </BrowserRouter>
  );
}
```

## 2. File-System Routing (Next.js App Router)
Modern industry standard. Pages are defined by folder hierarchies under the `app/` directory.
*   `app/page.tsx` matches `/`
*   `app/about/page.tsx` matches `/about`
*   `app/users/[id]/page.tsx` matches `/users/:id`

Supports **React Server Components (RSC)** by default, meaning components render on the server unless opted-out with `"use client"`.
