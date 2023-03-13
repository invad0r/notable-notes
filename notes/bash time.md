---
tags: [shell/bash/keyword]
title: bash time
created: '2019-08-02T08:39:11.840Z'
modified: '2022-06-16T10:55:57.225Z'
---

# bash time

> report time consumed by pipeline's execution

## flags

```sh
-p     # print the timing summary in the portable Posix format
```

## usage

```sh
time cat      # quick stop watch

# time goes over whole line pipes and redirects !
time grep '^#' ~/.bashrc | { i=0; while read -r; do printf '%4d %s\n' "$((++i))" "$REPLY"; done; } > bashrc_numbered 2>/dev/null
```

## see also

- [[time]]
- [[timeout]]
