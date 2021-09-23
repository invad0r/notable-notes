---
tags: [coreutils, macos]
title: rm
created: '2019-08-22T07:14:59.460Z'
modified: '2021-05-27T09:10:42.609Z'
---

# rm

> remove directory entries

## usage
```sh
rm -f  FILE     # ignore nonexistent files and arguments, never prompt

rm -r DIR       # remove all files contained within DIR recursively

rm -- -f        # remove file named `-f`

rm ./-f         # remove file named `-f`

rm \~           # no bash expantion from `~` to $HOMEDIR
```

## see also
- [[unlink]]
- [[bash]]
- [[mv]]
- [[cp]]
- [[rip]]
