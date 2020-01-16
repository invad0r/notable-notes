---
tags: [bash/built-in]
title: bash export
created: '2019-08-02T06:42:37.589Z'
modified: '2020-01-10T10:17:09.353Z'
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

## mutliple vairables
```sh
export A=1 B=2 C=3
```

## see also
- [[bash declare]]
