---
tags: [bash]
title: bash environment
created: '2019-07-30T06:19:48.998Z'
modified: '2019-07-30T06:22:29.787Z'
---

# bash environment

```sh
bash -x                 # dump what bash runs on startup http://superuser.com/a/144777

env

printenv

shopt -p                # show alle options

( set -o posix ; set ) | less   # set shows all shell variables (exported or not); -o posix => only variables
```
[What is the difference between 'env' and 'printenv' ?](https://unix.stackexchange.com/questions/123473/what-is-the-difference-between-env-and-printenv)
