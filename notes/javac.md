---
tags: [compiler, java]
title: javac
created: '2019-08-21T14:45:10.678Z'
modified: '2023-03-27T07:47:06.030Z'
---

# javac

> primary java compiler included in the `jdk` from oracle. Martin Odersky implemented the GJ compiler, and his implementation became the basis for javac[2]
> `javac` accepts source code conforming to the [[java]] language specification (JLS) and produces Java bytecode conforming to the Java Virtual Machine Specification (JVMS)
> `javac` is itself written in [[java]]. The compiler can also be invoked programmatically

## flag

```sh
--help,                 -help,                 -?         # print this help message
--help-extra,                                 -X          # print help on extra options
--boot-class-path PATH, -bootclasspath PATH               # override location of bootstrap class files
--class-path PATH,      -classpath PATH,      -cp PATH    # specify where to find user class files and annotation processors
--target RELEASE,       -target RELEASE                   # generate class files suitable for the specified java SE release
                        -deprecation                      # output source locations where deprecated APIs are used
--enable-preview                                          # enable preview language features. used in conjunction with either -source or --release
--source RELEASE,       -source RELEASE                   # provide source compatibility with the specified Java SE release
--release RELEASE                                         # compile for the specified Java SE release
                                              -g          # Generate all debugging info
                                              -d DIR      # specify where to place generated class files
                        -verbose                          # output messages about what the compiler is doing
--version,              -version                          # version information
                        -Werror                           # terminate compilation if warnings occur
```

## usage

```sh
javac -d . Foo.java   # -d specify directory for package, then call via `java foo.Foo`
```

## see also

- [[java]]
- [[javap]]
- [[ocamlc]]
- [[mvn]]
