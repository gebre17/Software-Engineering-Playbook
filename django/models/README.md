# Django Models & ORM

Models are the single, definitive source of information about your data. They contain the essential fields and behaviors of the data you're storing.

## 1. Defining Relationships
*   **One-to-Many (`ForeignKey`):** Standard relationship (e.g., Book has one Publisher, Publisher has many Books).
*   **Many-to-Many (`ManyToManyField`):** e.g., Book has many Authors, Author has many Books.
*   **One-to-One (`OneToOneField`):** e.g., User Profile extension of django's core User model.

```python
from django.db import models

class Author(models.Model):
    name = models.CharField(max_length=100)

class Book(models.Model):
    title = models.CharField(max_length=200)
    author = models.ForeignKey(Author, on_delete=models.CASCADE, related_name='books')
```

## 2. Django Migrations
Migrations are Django’s way of propagating changes you make to your models into your database schema.
*   `python manage.py makemigrations`: Creates new migration files based on changes detected in your models.
*   `python manage.py migrate`: Applies migration files to the database.

## 3. Query Optimization
Avoid the classic $N+1$ query problem using:
*   `select_related`: Performs a SQL JOIN and includes the fields of the related object in the SELECT statement. (Use for foreign keys and one-to-one).
*   `prefetch_related`: Does a separate lookup for each relationship and does the joining in Python. (Use for many-to-many and reverse foreign keys).

```python
# Instead of hitting DB on every iteration:
# books = Book.objects.all()
# Opt for:
books = Book.objects.select_related('author').all()
```
