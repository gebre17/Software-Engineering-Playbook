# Software Design Patterns

Design patterns are typical solutions to common problems in software design. Each pattern is like a blueprint that you can customize to solve a recurring design problem in your code.

## Classification of Patterns

### 1. Creational Patterns
Concerned with the process of object creation.
*   **Singleton:** Ensures a class has only one instance and provides a global point of access to it.
*   **Factory Method:** Defines an interface for creating an object, but lets subclasses decide which class to instantiate.
*   **Builder:** Separates the construction of a complex object from its representation.

### 2. Structural Patterns
Concerned with how classes and objects are composed to form larger structures.
*   **Adapter:** Allows incompatible interfaces to collaborate.
*   **Decorator:** Dynamically attaches additional responsibilities to an object.
*   **Proxy:** Provides a placeholder or surrogate for another object to control access to it.

### 3. Behavioral Patterns
Concerned with algorithms and the assignment of responsibilities between objects.
*   **Observer:** Defines a subscription mechanism to notify multiple objects about any events that happen to the object they're observing.
*   **Strategy:** Defines a family of algorithms, encapsulates each one, and makes them interchangeable.
*   **State:** Allows an object to alter its behavior when its internal state changes.

## Python Example: Strategy Pattern

```python
from abc import ABC, abstractmethod

# Strategy Interface
class PaymentStrategy(ABC):
    @abstractmethod
    def pay(self, amount):
        pass

# Concrete Strategies
class CreditCardPayment(PaymentStrategy):
    def pay(self, amount):
        print(f"Paying {amount} using Credit Card.")

class PayPalPayment(PaymentStrategy):
    def pay(self, amount):
        print(f"Paying {amount} using PayPal.")

# Context
class Order:
    def __init__(self, amount, payment_strategy: PaymentStrategy):
        self.amount = amount
        self.payment_strategy = payment_strategy

    def process(self):
        self.payment_strategy.pay(self.amount)
```
