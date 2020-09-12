---
tags: [dsl]
title: lua
created: '2020-09-02T12:55:03.179Z'
modified: '2020-09-02T13:19:31.132Z'
---

# lua

> lightweight, high-level, multi-paradigm programming language designed primarily for embedded use in applications
> was designed, to be integrated with software written in `c` and other conventional languages

## install
```sh
apt install build-essential libreadline-dev

curl -R -O http://www.lua.org/ftp/lua-${VERSION}.tar.gz
tar -zxf lua-${VERSION}.tar.gz && cd lua-${VERSION}
make linux test && make install
```

## usage
```sh
lua               # standalone interpreter and interactive shell

lua hello.lua     # run script
```

## see also
- [[luac]]
- [[luarocks]]
- [[tcl]]
- [[awk]]
- [[groovy]]
- [lua.org/pil/contents.html](https://www.lua.org/pil/contents.html)
- [[nginx]]
