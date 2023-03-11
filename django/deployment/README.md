# Django Deployment

A production readiness guide for Django web applications.

## WSGI vs. ASGI

*   **WSGI (Web Server Gateway Interface):** Synchronous standard. (e.g., Gunicorn, uWSGI).
*   **ASGI (Asynchronous Server Gateway Interface):** Asynchronous standard. Required if using WebSockets (Django Channels) or async views. (e.g., Uvicorn, Daphne).

## Security Checklist (`settings.py`)
```python
# Disable debugging mode in production
DEBUG = False

# Restrict host headers
ALLOWED_HOSTS = ['yourdomain.com']

# Secure cookies & redirection
SECURE_SSL_REDIRECT = True
SESSION_COOKIE_SECURE = True
CSRF_COOKIE_SECURE = True
```

## Static & Media File Delivery
Django does not serve static files efficiently in production.
*   **WhiteNoise:** Integrates with WSGI/ASGI to serve static assets directly from Python.
*   **Cloud Storage:** Offload media uploads (user files) to AWS S3, Google Cloud Storage, or Azure Blob using `django-storages`.
