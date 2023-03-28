---
tags: [c]
title: ld
created: '2020-04-24T08:59:03.868Z'
modified: '2023-03-25T12:40:13.980Z'
---

# ld

>  gmi linker - combines object and archive files, relocates their data and ties up symbol references. Usually the last step in compiling a program

## usage

```sh
ld main.o -lc   # tell the linker to include `libc`

# produce a file OUTPUT as the result of linking `/lib/crt0.o` with `hello.o` and the library `libc.a`, which will come from the standard search directories.
ld -o OUTPUT /lib/crt0.o hello.o -lc
```

## see also

- [[ldd]]
- [[gcc]]
- [linux.die.net/man/1/ld](https://linux.die.net/man/1/ld)
