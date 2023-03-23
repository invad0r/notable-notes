---
tags: [compiler, java]
title: javac
created: '2019-08-21T14:45:10.678Z'
modified: '2023-03-22T08:25:36.652Z'
---

# javac

> primary java compiler included in the `jdk` from oracle. Martin Odersky implemented the GJ compiler, and his implementation became the basis for javac[2]
> `javac` accepts source code conforming to the Java language specification (JLS) and produces Java bytecode conforming to the Java Virtual Machine Specification (JVMS).
> javac is itself written in Java. The compiler can also be invoked programmatically

## usage

```sh
javac -d . Foo.java   # -d specify directory for package
                      # call via `java foo.Foo`
```

## see also
- [[java]]
- [[javap]]
- [[ocamlc]]
- [[mvn]]
