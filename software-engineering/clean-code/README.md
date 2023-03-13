# Clean Code Best Practices

Clean code is reader-focused, easy to understand, easy to change, and has standard conventions.

## Core Rules

### 1. Naming Conventions
*   **Use Intent-Revealing Names:** Names should describe the purpose of variables, functions, and classes.
*   **Pronounceable & Searchable Names:** Avoid abbreviations like `d` for days. Use `days_since_creation`.
*   **Function Names should be Verbs:** Use `calculate_total` instead of `total`.
*   **Class Names should be Nouns:** Use `UserAccount` instead of `ManagingUsers`.

### 2. The SOLID Principles
*   **Single Responsibility Principle (SRP):** A class should have one, and only one, reason to change.
*   **Open/Closed Principle (OCP):** Software entities should be open for extension, but closed for modification.
*   **Liskov Substitution Principle (LSP):** Subtypes must be substitutable for their base types.
*   **Interface Segregation Principle (ISP):** Clients should not be forced to depend on methods they do not use.
*   **Dependency Inversion Principle (DIP):** Depend on abstractions, not on concretions.

### 3. Function Design
*   **Small:** Keep functions focused on doing one thing.
*   **Few Arguments:** Limit function parameters (ideally 0-2). Use configuration objects/data classes if more are needed.
*   **No Side Effects:** A function should not alter global state unexpectedly.

### 4. DRY (Don't Repeat Yourself)
Every piece of knowledge or logic must have a single, unambiguous representation within a system.
