---
tags: [shell/bash/builtin]
title: bash alias
created: '2019-08-02T06:42:37.554Z'
modified: '2022-04-06T11:38:03.695Z'
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
- [cyberciti.biz/tips/bash-aliases-mac-centos-linux-unix/](https://www.cyberciti.biz/tips/bash-aliases-mac-centos-linux-unix.html/)
