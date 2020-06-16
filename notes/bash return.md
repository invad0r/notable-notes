---
tags: [bash/built-in]
title: bash return
created: '2019-08-02T06:42:37.626Z'
modified: '2020-05-05T06:50:55.383Z'
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
