## When to use decorators?

It's an implementation of OOP's Open-close principle (Open for extension, closed for modification).
It can be used to reduce number of subclasses created when slight modifications are required. It uses _composition_ pattern rather than _inheritance_.

_NOTE: it can cause maintenance overhead (too many small decorators to maintain)_

e.g.
with inherintance, a beverage item can look something like:
Subclasses:

1. Coffee
2. Coffee+Sugar
3. Coffee+Sugar+Milk

With decorators, a beverage item will look something like:
Subclasses:

1. Coffee

Decorators:

1. Sugar
2. Milk
