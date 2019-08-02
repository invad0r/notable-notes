---
tags: [bash]
title: bash type
created: '2019-07-30T06:19:49.022Z'
modified: '2019-07-30T06:22:29.803Z'
---

# bash type

> A `builtin` is a command provided by the shell, rather than by an external program 
[bash - What is the difference between a builtin command and one that is not? - Unix & Linux Stack Exchange](http://unix.stackexchange.com/a/11456)

```sh
type ls         # find out if command is avail and if builtin

command -V ls   # same as above


type -F         # list functions
```
