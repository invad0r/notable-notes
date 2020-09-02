---
tags: [coreutils]
title: dirname
created: '2020-09-01T07:57:37.197Z'
modified: '2020-09-01T12:43:12.329Z'
---

# dirname

> removes last level or filename from a given pathname

## usage
```sh
dirname /foo/bar/baz                    # returns `/foo/bar`

CURRENTDIR="$(cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"
```

## see also
- [[bash pwd]]
- [[basename]]
