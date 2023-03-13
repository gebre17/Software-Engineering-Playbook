# Testing Strategies

Software testing ensures code reliability, prevents regressions, and helps document expected behavior.

## The Testing Pyramid

```
      / \
     /   \     UI/End-to-End Tests (Fewest)
    /-----\
   /       \   Integration/API Tests
  /---------\
 /           \ Unit Tests (Most)
 -------------
```

### 1. Unit Tests
*   Verify the smallest testable parts of an application (e.g., functions, class methods) in isolation.
*   *Mocks and Stubs:* Used to isolate external dependencies (databases, API clients).

### 2. Integration Tests
*   Verify that multiple units or systems work together correctly (e.g., verifying that a view successfully writes to a PostgreSQL database).

### 3. End-to-End (E2E) / UI Tests
*   Test the entire system flow from the user interface down to the database (e.g., using Cypress, Playwright, or Selenium).

## Test-Driven Development (TDD)
A development cycle of writing tests first, watching them fail, writing minimal code to make them pass, and refactoring:
1.  **Red:** Write a failing test.
2.  **Green:** Write minimum code to pass the test.
3.  **Refactor:** Clean up code while ensuring tests stay green.
