---
tags: [shell/bash/builtin]
title: bash help
created: '2019-08-02T06:42:37.601Z'
modified: '2022-11-25T10:57:31.810Z'
---

# bash help

> display information about builtin commands

## flag

```sh
-d              # output short description
-m              # display usage in pseudo-manpage format
-s              # output only a short usage synopsis for each topic matching PATTERN
```

## usage

```sh
help            # displays brief summaries of builtin commands

help CMD        # find out more about the function CMD

man -k          # find out more about commands not in this list
info            # find out more about commands not in this list
info bash       # find out more about the shell in general
```

## see also

- [[man]]
- [[command-not-found]]
- [[bash \[\[]]
