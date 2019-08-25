---
tags: [bash/builtin]
title: bash export
created: '2019-08-02T06:42:37.589Z'
modified: '2019-08-20T07:21:21.957Z'
---

# bash export

> export will make variables/functions available to all shells forked from the current shell.


```sh
-n        remove the export property from each NAME
```

`declare -x`

# pass function to any child processes
```sh
export -f myFunc
```

## list exported variables and functions
```sh
export -p
```
see also [[bash declare]]

## mutliple vairables
```sh
export A=1 B=2 C=3
```
