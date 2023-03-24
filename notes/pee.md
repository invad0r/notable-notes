---
tags: [linux, moreutils]
title: pee
created: '2020-09-01T07:26:48.805Z'
modified: '2023-03-22T08:28:05.128Z'
---

# pee

> pee - tee standard input to pipes

## usage

```sh
echo "Hello world" | pee cat cat    #  redirects to multiple secondary commands

cat file | pee 'sort -u > sorted' 'sort -R > unsorted'
```

## see also

- [[tee]]
- [[moreutils]]
- [[sort]]
