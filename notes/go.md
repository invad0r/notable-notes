---
tags: [lang/go]
title: go
created: '2019-07-30T06:19:49.075Z'
modified: '2019-07-30T08:02:09.500Z'
---

# go

- it's `staticallly typed` and `garbage collected`

```
  has                             doesn't have

+ package system                - implicit numeric conversion
+ first-class-functions         - constructors/destructors
+ lexical-scope                 - operator overloading
+ system call interface         - default parameter values
+ immutable string in utf-8     - inheritance (type-based inheritance → subclasses)
                                - generics    `parametrics polimorphism` ≈ `generics`
                                - exceptions
                                - macros
                                - function annotations
                                - thread local storag
```

---

+ type system
+ concurrency support (concurrency based on CSP)

types expected if upperase
struct ~ class

no inheritance but composition of type

no explicit declaration interface-implementation required

---

# semicolon rule

`;` terminates statements

if last token before new line:
- is an `identifiere` -> int float64
- is an `basic literal` -> number, string
- or a `token` -> break, continues, fallthrough, retrun, ++, --, ), }

if the new line comes after a `token` that could end the statemtn => insert a `;`
