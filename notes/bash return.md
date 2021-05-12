---
tags: [shell/bash/builtin]
title: bash return
created: '2019-08-02T06:42:37.626Z'
modified: '2021-05-12T08:46:08.376Z'
---

# bash return

> return from a shell function
> Causes a function or sourced script to exit with the return value specified by N.  
> If N is omitted, the return status is that of the last command executed within the function or script.

## usage
```sh
foo() {
  return 1;
}
```

## see also
- [[bash exit]]
- [[bash function]]
