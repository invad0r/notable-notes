---
tags: [c, compiler]
title: gcc
created: '2019-07-30T06:19:49.029Z'
modified: '2020-02-21T08:51:01.686Z'
---

# gcc

> `gnu compiler collection` includes front ends for `c`, `c++`, `objective-C`, Fortran, Ada, [[go]], and D, as well as libraries for these languages (libstdc++,...). 
> `gcc` was originally written as the compiler for the GNU operating system.

```
step:    pre-processing  => compiling => assembly => linking
output:  file.i          => file.s    => ile.o    => file
```

## usage
```sh
gcc -o file file.c                  # creates dynamically linked binary

gcc -o hello hello.c -static        # creates static binary

gcc -Wall -g -O0 -o file file.c


gcc -xc++ -lstdc++ -shared-libgcc   # equivalent to g++
```

## see also
- [[g++]]
- [[ldd]]
- [[go]]
