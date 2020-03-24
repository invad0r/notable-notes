---
tags: [linux]
title: basename dirname
created: '2019-10-04T07:16:41.100Z'
modified: '2020-03-16T17:18:38.371Z'
---

# basename dirname

> return filename or directory portion of pathname

## usage
```sh
basename -s .log $(ls /var/log/*.log)   # get only filename stripped from extension

dirname /foo/bar/baz                    # returns `/foo/bar`

CURRENTDIR="$(cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"
```

## see also
- [[bash pwd]]
