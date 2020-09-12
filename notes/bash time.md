---
tags: [bash/keyword]
title: bash time
created: '2019-08-02T08:39:11.840Z'
modified: '2020-09-09T09:04:04.600Z'
---

# bash time

> report time consumed by pipeline's execution

## usage
```sh
-p     # print the timing summary in the portable Posix format


time cat      # quick stop watch


# time goes over whole line pipes and redirects !
time grep '^#' ~/.bashrc | { i=0; while read -r; do printf '%4d %s\n' "$((++i))" "$REPLY"; done; } > bashrc_numbered 2>/dev/null
```

## see also
- [[bash times]]
- [[time]]
- [[bash built-in vs keyword]]
- [[timeout]]
