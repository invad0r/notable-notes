---
tags: [c]
title: dtrace
created: '2020-03-13T13:14:20.494Z'
modified: '2023-03-25T12:42:08.758Z'
---

# dtrace

## usage

```sh
man -k dtrace

dtrace -l -P 'hyperkit$target' -p $(pgrep -f hyperkit)
```

## see also

- [[hyperkit]]
- [[strace]]
- [[signal]]
