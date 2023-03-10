# React Projects & Boilerplate Layouts

Guides on how to initialize and structure React applications.

## Initializing a React App

### 1. Single Page Application (using Vite)
```bash
npm create vite@latest my-app -- --template react-ts
cd my-app
npm install
npm run dev
```

### 2. Full-Stack/SSR Application (using Next.js)
```bash
npx create-next-app@latest my-app --typescript --tailwind --eslint
```

## Standard Folder Structure

```
src/
├── assets/          # Images, static vectors, styles
├── components/      # Reusable UI components (Buttons, InputFields)
├── hooks/           # Custom React hooks (useAuth, useLocalStorage)
├── pages/           # Page-level route views
├── services/        # API client modules and requests
├── store/           # Global state management configuration (Zustand, Redux)
├── utils/           # Helper scripts and generic utility functions
├── App.tsx          # Root Application Component
└── main.tsx         # Application Entrypoint
```
