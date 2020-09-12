---
tags: [linux]
title: readlink
created: '2020-01-14T06:52:48.775Z'
modified: '2020-09-02T17:53:06.452Z'
---

# readlink
> used to print resolved symbolic links or canonical file names.
## usage
```sh
readlink -f desk1   # canonicalize by following every symlink in every component of the given name recursively

readlink -n file    # do not output the trailing delimiter
```

## see also
- [[stat]]
- [[ln]]
