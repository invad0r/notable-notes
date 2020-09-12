---
tags: [Notebooks]
title: solid principles
created: '2020-02-01T08:30:02.163Z'
modified: '2020-09-02T17:44:36.559Z'
---

# solid principles

> five object-oriented design principles by Robert C. Martin aka Uncle Bob.

```
S O L I D
| | | | └─ Dependency Inversion Principe
| | | └─── Interface Segregation Principle
| | └───── Liskov Substituation Principle
| └─────── Open Close Principle
└───────── Single Responsibility Principle
```

## Single Responsibility Principle
A class should have one and only one reason to change, meaning that the class should have only one job.

## Open-Closed Principle
Objects or Entities should be open for extension, but closed for modification

## Liskov Substitution Principle
Let q(x) be a property provable about objects of x of Type T. Then q(y) should be provable for objects y of type S where S is substitute of T.

## Interface Segregation Principle
A client should never be forced to implement an interface that it doesn't use or clients shouldn't be forced to depend on methods they do not use.

## Dependency Inversion Principle
Entities must depend on abstractions not on concretions. It states that high level module must not depend on the low level module, but they should depend on abstractions.  => allows for decoupling


## see also
- [[software design pattern]]
