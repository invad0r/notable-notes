---
tags: [c, compiler]
title: gcc
created: '2019-07-30T06:19:49.029Z'
modified: '2020-05-16T09:42:26.362Z'
---

# gcc

> `gnu compiler collection` includes front ends for `c`, `c++`, `objective-C`, Fortran, Ada, [[go]], and D, as well as libraries for these languages (libstdc++,...). 
> `gcc` was originally written as the compiler for the GNU operating system.

```
step:    pre-processing  => compiling => assembly => linking
output:  file.i          => file.s    => ile.o    => file
```

## install
`yum -y install gcc`

## usage
```sh
# options
# -o FILE     output file
# -WTYPE      warning

gcc -o file file.c                  # creates dynamically linked binary

gcc -o file file.c -static          # creates static binary

gcc -g file.c                       # add debugging symbols for gdb

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
```

## see also
- [[g++]]
- [[ldd]]
- [[go]]
- [[make]]
- [[gdb]]
