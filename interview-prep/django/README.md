# Django Interview Prep

Common architectural and optimization questions for Django roles.

## Core Questions

### 1. Explain the Django Request-Response Lifecycle
1.  **Request Entry:** Web server (Nginx) forwards request to WSGI/ASGI server (Gunicorn/Uvicorn).
2.  **Middleware:** Request passes through `MIDDLEWARE` list sequentially (`process_request` / `__call__`).
3.  **URL Resolver:** Match URL pattern to the correct view.
4.  **View Execution:** View executes business logic, interacts with database via ORM, and formats response.
5.  **Middleware (Response):** Response traverses middleware list in reverse order.
6.  **Response Return:** Response goes back to web server and client.

### 2. How do you optimize slow Django API endpoints?
*   Analyze SQL queries using `django-debug-toolbar` or `django-silk`.
*   Reduce database query count via `select_related` and `prefetch_related`.
*   Add indexes to query criteria fields.
*   Introduce caching (Redis) for slow, static computations or page blocks.
*   Offload slow operations (e.g., sending emails, generating reports) to background tasks via Celery.
