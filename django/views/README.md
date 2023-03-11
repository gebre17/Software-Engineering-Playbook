# Django Views

Views are Python functions or classes that receive web requests and return web responses (such as HTML documents, redirects, or JSON).

## FBVs vs. CBVs

### 1. Function-Based Views (FBVs)
*   Simple, direct, and explicit. Excellent for lightweight or unique logic.
*   *Downside:* Can lead to duplicate boilerplates across views.

```python
from django.shortcuts import render, get_object_or_404
from .models import Book

def book_detail(request, pk):
    book = get_object_or_404(Book, pk=pk)
    return render(request, 'books/detail.html', {'book': book})
```

### 2. Class-Based Views (CBVs)
*   Leverage inheritance and mixins to eliminate boilerplate logic.
*   *Downside:* Harder to read and trace due to deep method resolution chains.

```python
from django.views.generic import DetailView
from .models import Book

class BookDetailView(DetailView):
    model = Book
    template_name = 'books/detail.html'
    context_object_name = 'book'
```

## Middleware
Hooks that run before a request reaches the view, or after the view returns a response.
*   *Uses:* Custom authentication check, rate limiting, request tracking, logging.
*   Must implement `__call__(request)` method returning a response.
