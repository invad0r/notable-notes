---
tags: [shell/bash/builtin]
title: bash readonly
created: '2019-08-02T06:42:37.624Z'
modified: '2022-02-10T09:07:55.251Z'
---

# bash readonly

> mark shell variables as unchangeable

## usage

```sh
-a        # refer to indexed array variables
-A        # refer to associative array variables
-f        # refer to shell functions
-p        # display a list of all readonly variables or functions, depending on whether or not the -f option is given

--        #  disables further option processing
```

```sh
readonly
```

## see also

- [[bash export]]
- [[bash set]]
- [[bash unset]]
