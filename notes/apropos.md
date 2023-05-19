---
tags: [linux, macos]
title: apropos
created: '2019-09-23T05:22:20.385Z'
modified: '2023-05-19T11:12:34.655Z'
---

# apropos

> search the whatis database for strings

## usage

```sh
apropos namespace    # searches for man pages with namespaces

apropos -e fork       # limit exact word
apropos "^fork$"
```

## see also

- [[man]], [[whatis]]
- [[which]]
- [[type]]
- [[command-not-found]]
