---
tags: [macos]
title: mdfind
created: '2020-12-24T15:03:39.240Z'
modified: '2021-10-01T11:42:23.989Z'
---

# mdfind

> anything spotlight finds, mdfind can find,  includes ability to search inside files and metadata

## usage

```sh
# -onlyin     restrict the search to a single dir

mdfind -onlyin ~/Documents essay

mdutil -E w         # erase index and rebuild from scratch

mdutil -i off       # turn off indexing entirely with 
```

## see also

- [[mdutil]]
- [[locate]]
- [[macos keyboard shortuts]]
