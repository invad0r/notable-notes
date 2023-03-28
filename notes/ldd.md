---
tags: [c]
title: ldd
created: '2020-02-21T08:19:15.513Z'
modified: '2023-03-25T12:40:27.602Z'
---

# ldd

> print shared library dependencies 

## usage

```sh
ldd file    # prints libraries program needs

ldd a.out
#        linux-vdso.so.1 (0x00007ffe97fc9000)
#        libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007f18638a7000)
#        /lib64/ld-linux-x86-64.so.2 (0x00007f1863a74000)
```

## see also

- [[ld]]
- [[gcc]]
- [[nm]]
