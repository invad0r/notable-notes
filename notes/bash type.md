---
tags: [shell/bash]
title: bash type
created: '2019-07-30T06:19:49.022Z'
modified: '2021-05-12T08:46:51.330Z'
---

# bash type

> A `builtin` is a command provided by the shell, rather than by an external program 

## usage
```sh
type ls         # find out if command is avail and if builtin

type -t type    # single word which is one of `alias`, `keyword`, `function`, `builtin`, `file` or ``
                # if NAME is an alias, shell reserved word, shell function, shell builtin, disk file, or not found, respectivel

command -V ls   # same as above

type -F         # list functions

type -a time   # all locations containing an executable named
# time is a shell keyword
# time is /usr/bin/time
```

## see also
- [[bash compgen]]
- [[bash command]]
- [[which]]
- [What is the difference between a builtin command and one that is not?](http://unix.stackexchange.com/a/11456)
- [https://askubuntu.com/a/1054460/219213](https://askubuntu.com/a/1054460/219213)
