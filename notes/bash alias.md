---
tags: [bash/built-in]
title: bash alias
created: '2019-08-02T06:42:37.554Z'
modified: '2020-09-09T08:24:41.551Z'
---

# bash alias

## usage
```sh
alias l='ls -l'   # define alias

alias -p          # print all defined aliases in a reusable format


# use alias to intercept to change future invocation
ls
alias ls='/usr/bin/time ls'
ls
unalias ls
```
## see also
- [[bash unalias]]
- [[git log]]
- [[time]]
