---
tags: [macos]
title: mdfind
created: '2020-12-24T15:03:39.240Z'
modified: '2023-05-19T17:44:29.016Z'
---

# mdfind

> anything spotlight finds, mdfind can find,  includes ability to search inside files and metadata

## usage

```sh
-onlyin     # restrict the search to a single dir
```

## usage

```sh
mdfind -onlyin ~/Documents essay

mdutil -E w         # erase index and rebuild from scratch

mdutil -i off       # turn off indexing entirely with 
```

## see also

- [[defaults]]
- [[mdutil]]
- [[locate]]
- [[macos keyboard shortuts]]
