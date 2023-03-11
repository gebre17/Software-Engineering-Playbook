# Django Authentication

Robust authentication architectures in Django applications.

## Custom User Model
Always define a custom user model at the start of a project, even if the default User model is sufficient initially.

```python
# models.py
from django.contrib.auth.models import AbstractUser
from django.db import models

class CustomUser(AbstractUser):
    bio = models.TextField(max_length=500, blank=True)
    birth_date = models.DateField(null=True, blank=True)
```

And define it in `settings.py`:
```python
AUTH_USER_MODEL = 'users.CustomUser'
```

## Auth Approaches for APIs

### 1. Token Authentication (Built-in DRF)
*   Standard token assigned to user. Sent in `Authorization: Token <key>` header.
*   *Downside:* Simple; token does not expire unless deleted from DB manually.

### 2. JWT (JSON Web Tokens)
*   Stateless authentication. Uses Access Tokens (short-lived) and Refresh Tokens (longer-lived).
*   *Library:* `djangorestframework-simplejwt` is the industry standard.

### 3. Session Authentication
*   Default web auth using cookies. Useful for single-page applications sharing the same root domain.
