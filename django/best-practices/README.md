# Django Best Practices

A compilation of design patterns and architecture guidelines for production-grade Django projects.

## 1. Project Layout & Settings Separation
Separate your setting files by environment (Local, Staging, Production).

```
myproject/
├── settings/
│   ├── __init__.py
│   ├── base.py
│   ├── local.py
│   └── production.py
```

Load custom configs dynamically using environment variables via `django-environ` or `python-decouple`.

## 2. Fat Models, Thin Views (or Services Pattern)
*   Keep view logic focused strictly on HTTP requests, status codes, and routing.
*   Encapsulate database query logic inside custom managers/querysets.
*   Use a **Services Layer** (`services.py`) for complex business logic involving multiple models or third-party integrations.

## 3. Database Indexes
Always index fields that are frequently queried (e.g., in `.filter()`, `.exclude()`, or `order_by()`).

```python
class Post(models.Model):
    title = models.CharField(max_length=200)
    created_at = models.DateTimeField(auto_now_add=True, db_index=True)
```
