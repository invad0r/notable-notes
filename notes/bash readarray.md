---
tags: [shell/bash/builtin]
title: bash readarray
created: '2019-08-02T06:42:37.622Z'
modified: '2021-10-25T09:43:51.075Z'
---

# bash readarray

> synonym for [[bash mapfile]] - read lines from a FILE into an array variable

## usage

```sh
-d delim
-n count
-O origin
-s count
-t
-u fd
-C callback
-c quantum
```

```sh
readarray ARRAY < <(yq e '.coolActions[]' sample.yaml)
 echo "${ARRAY[1]}"
```

## see also

- [[bash array]]
- [[yq]]
