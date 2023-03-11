# Django REST Framework (DRF)

Django REST Framework (DRF) is a powerful and flexible toolkit for building Web APIs in Django.

## Core Pillars

### 1. Serializers
Define how model instances are converted to Python primitives and validated before saving.

```python
from rest_framework import serializers
from .models import Book

class BookSerializer(serializers.ModelSerializer):
    class Meta:
        model = Book
        fields = ['id', 'title', 'author']
```

### 2. ViewSets & Routers
Combine the logic for multiple related views into a single class (e.g., standard CRUD operations: List, Create, Retrieve, Update, Destroy).

```python
from rest_framework import viewsets
from .models import Book
from .serializers import BookSerializer

class BookViewSet(viewsets.ModelViewSet):
    queryset = Book.objects.all()
    serializer_class = BookSerializer
```

And route automatically using a router in `urls.py`:
```python
from rest_framework.routers import DefaultRouter
from .views import BookViewSet

router = DefaultRouter()
router.register(r'books', BookViewSet, basename='book')
urlpatterns = router.urls
```

### 3. Permissions & Throttling
*   **Permissions:** Restrict access (e.g., `IsAuthenticated`, `IsAdminUser`, or custom permissions like `IsOwnerOrReadOnly`).
*   **Throttling:** Limit request rate to prevent abuse (e.g., AnonRateThrottle, UserRateThrottle).
