---
tags: [bash/built-in]
title: bash shopt
created: '2019-07-30T06:19:49.237Z'
modified: '2020-01-17T07:51:37.711Z'
---

# bash shopt

> Historically, the set command was used to turn options on and off. As the number of options grew, set became more difficult to use because options are represented by single letter codes. As a result, Bash provides the `shopt` command to turn options on and off by name instead of a letter. 

## usage
```sh
# set-and-unset-shell-options:
#   -s     set, enable
#   -u     unset, disable
#   -q     quite mode
#   -p     print


shopt -p    # print all options


shopt -p cdspell
#  shopt -u cdspell    # is unset -u

shopt -p promptvars
#  shopt -s promptvars  # is set -s
```

## see also
- [[bash]]
- [[env]]
