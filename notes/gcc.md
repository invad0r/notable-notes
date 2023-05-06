---
tags: [c, compiler, linux, macos]
title: gcc
created: '2019-07-30T06:19:49.029Z'
modified: '2023-05-04T13:51:42.073Z'
---

# gcc

> `gnu compiler collection` includes front ends for `c`, `c++`, `objective-C`, Fortran, Ada, [[go]], and D, as well as libraries for these languages (libstdc++,...). 
> `gcc` was originally written as the compiler for the GNU operating system.

```
step:    pre-processing  => compiling => assembly => linking
output:  file.i          => file.s    => ile.o    => file
```

## install

```sh
yum -y install gcc
```

## option

```sh
-o FILE     # output file
-WTYPE      # warning
-g FILE     # add debugging symbols for gdb
```

## usage

```sh
gcc -o file file.c                  # creates dynamically linked binary

gcc -o file file.c -static          # creates static binary

gcc -c file.c           # generates      "object file": `file.o`; only run preprocess, compile, and assemble steps
gcc file.o              # generates "assembler output": `a.out`
ld file.o -lc           # link to `libc`

gcc -Wall -g -O0 -o file file.c


gcc -xc++ -lstdc++ -shared-libgcc   # equivalent to g++

gcc -dM -E - < /dev/null                          # dump preprocessor defines / macros
gcc -E -dM -include sys/socket.h - < /dev/null    # dump preprocessor defines of header file

$(gcc -print-prog-name=cpp) -v </dev/null         # where gcc looks for header-files
echo "#include <limits.h>" > t.c; gcc -v t.c; rm t.c
LC_ALL=C gcc -v -E -xc - < /dev/null 2>&1 | LC_ALL=C sed -ne '/starts here/,/End of/p'

echo | gcc -E -xc -include 'stddef.h' - | grep size_t     # lookup type of size_t
# typedef long unsigned int size_t;
```

## see also

- [[cc]]
- [[g++]]
- [[ld]]
- [[ldd]]
- [[go]]
- [[nm]]
- [[make]]
- [[gdb]]
