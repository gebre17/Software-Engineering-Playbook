# Web Security

Web security refers to the protective measures and protocols implemented to safeguard web applications from malicious attacks.

## Core Defense Headers

### 1. CORS (Cross-Origin Resource Sharing)
Restricts which external domains are allowed to read responses from a backend API.
```http
Access-Control-Allow-Origin: https://trusteddomain.com
Access-Control-Allow-Methods: GET, POST, OPTIONS
```

### 2. CSP (Content Security Policy)
Restricts from which domains scripts, stylesheets, and images can be loaded and executed, mitigating Cross-Site Scripting (XSS).
```http
Content-Security-Policy: default-src 'self'; script-src 'self' https://trustedapis.com;
```

### 3. HSTS (HTTP Strict Transport Security)
Instructs browsers to access the site strictly using HTTPS instead of HTTP.
```http
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
```

### 4. Secure Cookie Flags
Ensure session identifiers are stored safely.
*   `Secure`: Cookie is only transmitted over encrypted connections (HTTPS).
*   `HttpOnly`: Cookie cannot be accessed by client-side scripts, protecting it from theft via XSS.
*   `SameSite`: Controls whether cookies are sent with cross-site requests. Set to `Strict` or `Lax`.
