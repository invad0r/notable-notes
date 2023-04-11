---
tags: [lua, packagemanager]
title: luarocks
created: '2020-09-02T13:03:43.096Z'
modified: '2023-04-11T20:14:40.089Z'
---

# luarocks

> package manager for lua modules

## install

```sh
wget https://luarocks.org/releases/luarocks-${VERSION}.tar.gz
tar zxpf luarocks-${VERSION}.tar.gz
cd luarocks-${VERSION}
```

## usage

```sh
luarocks                      #  see the available commands

luarocks help install         # get help on command

luarocks install dkjson       # installing packages

luarocks make
```

## see also
- [[lua]]
- [[luac]]
- [[make]]
