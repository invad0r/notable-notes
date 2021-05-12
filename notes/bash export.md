---
tags: [shell/bash/builtin]
title: bash export
created: '2019-08-02T06:42:37.589Z'
modified: '2021-05-12T08:46:07.952Z'
---

# bash export
> export will make variables/functions available to all shells forked from the current shell.

## usage
```sh
export -p               # list exported variables and functions, same as `declare -x`

export -n               # remove the export property from each NAME

export -f myFunc        # pass function to any child processes

export A=1 B=2 C=3      # mutliple vairables
```

## see also
- [[bash declare]]
- [[heredoc]]
