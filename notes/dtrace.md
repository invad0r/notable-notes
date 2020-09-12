---
tags: [c]
title: dtrace
created: '2020-03-13T13:14:20.494Z'
modified: '2020-09-02T18:07:01.802Z'
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
