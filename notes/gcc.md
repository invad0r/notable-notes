---
tags: [c, compiler]
title: gcc
created: '2019-07-30T06:19:49.029Z'
modified: '2019-08-21T14:44:36.070Z'
---

# gcc

> `gnu compiler collection` includes front ends for `c`, `c++`, `objective-C`, Fortran, Ada, [[go]], and D, as well as libraries for these languages (libstdc++,...). 
> `gcc` was originally written as the compiler for the GNU operating system.

[[g++]]

```
1. pre-processing  =>  2. compiling    =>  3. assembly     => 4. linking
   output: file.i  =>  output: file.s  =>  output:file.o   => output: file
```

```sh
gcc -o file_sum file_sum.c

gcc -Wall -g -O0 -o file_sum file_sum.c
```
