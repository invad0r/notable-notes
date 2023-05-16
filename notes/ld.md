---
tags: [c]
title: ld
created: '2020-04-24T08:59:03.868Z'
modified: '2023-05-09T07:00:49.120Z'
---

# ld

>  gmi linker - combines object and archive files, relocates their data and ties up symbol references. Usually the last step in compiling a program

## option

```sh

```

## usage

```sh
ld main.o -lc     # tell the linker to include `libc`

# produce a file OUTPUT as the result of linking `/lib/crt0.o` with `hello.o` and the library `libc.a`, which will come from the standard search directories.
ld -o OUTPUT /lib/crt0.o hello.o -lc

ld -macosx_version_min $(MACOS_VERSION) -o FILE FILE.o \
  -lSystem -syslibroot $(xcrun -sdk macosx --show-sdk-path) -e _start -arch arm64
```

## see also

- [[as]]
- [[make]]
- [[xcrun]]
- [[ldd]]
- [[gcc]]
- [linux.die.net/man/1/ld](https://linux.die.net/man/1/ld)
