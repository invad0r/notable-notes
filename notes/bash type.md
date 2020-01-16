---
tags: [bash]
title: bash type
created: '2019-07-30T06:19:49.022Z'
modified: '2020-01-15T10:02:48.637Z'
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
```

## see also
- [[bash command]]
- [[which]]
- [What is the difference between a builtin command and one that is not?](http://unix.stackexchange.com/a/11456)
