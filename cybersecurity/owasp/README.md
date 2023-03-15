# OWASP Top 10 Web Vulnerabilities

A guide to the most critical security risks facing modern web applications and their mitigations.

## 1. SQL Injection (SQLi)
*   **What it is:** Malicious SQL statements are injected into entry fields for execution (e.g., executing raw query string concatenation).
*   **Mitigation:** Use parameterized queries or Object-Relational Mappers (ORMs). Never concatenate input directly into SQL queries.

```python
# VULNERABLE
cursor.execute(f"SELECT * FROM users WHERE username = '{user_input}'")

# SECURE
cursor.execute("SELECT * FROM users WHERE username = %s", [user_input])
```

## 2. Cross-Site Scripting (XSS)
*   **What it is:** Malicious scripts are injected into trusted web pages and executed within the victim's browser.
*   **Mitigation:** Sanitize and escape all user input before rendering. Implement strict Content Security Policies (CSP) and use `HttpOnly` cookie flags.

## 3. Cross-Site Request Forgery (CSRF)
*   **What it is:** Forces an authenticated user to execute unwanted actions on a web application in which they're currently authenticated.
*   **Mitigation:** Use CSRF Tokens. Ensure GET requests do not alter state (use POST/PUT/DELETE for mutating operations) and set `SameSite=Lax` or `SameSite=Strict` on cookies.
