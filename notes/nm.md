---
title: nm
created: '2020-04-24T09:04:34.811Z'
modified: '2020-04-24T09:06:44.164Z'
---

# nm

> list symbols from object files

## usage
```sh
nm main.o

nm -D /lib/x86_64-linux-gnu/libc-2.13.so | grep printf    #  find out what symbols are in a library
```

## see also
- [[gcc]]
- [[ldd]]
- [[ld]]
