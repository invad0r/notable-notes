---
tags: [bash/built-in]
title: bash unset
created: '2019-08-02T06:42:37.651Z'
modified: '2020-01-10T10:17:10.005Z'
---

# bash unset

> Unset values and attributes of shell variables and functions.

[[bash set]]


## options
```sh
unset -f    # treat each NAME as a shell function
unset -v    # treat each NAME as a shell variable
unset -n    # treat each NAME as a name reference and unset the variable itself rather than the variable it references
```
Without options, unset first tries to unset a variable, and if that fails,tries to unset a function.

Some variables cannot be unset; also see `readonly'.
