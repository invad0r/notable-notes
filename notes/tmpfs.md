---
tags: [filesystem]
title: tmpfs
created: '2020-02-20T09:44:43.272Z'
modified: '2021-03-19T10:42:16.213Z'
---

# tmpfs

> temporary filesystem that resides in memory and/or swap partition - way of speeding up accesses to files or automatically clearing on reboot

## usage

```sh
findmnt /tmp

cd "$(mktemp -d)"     # change to random temp-dir for testing
```

## see also

- [[filesystem hierarchy standard]]
- [[df]]
- [[mount]]
- [[findmnt]]
- [[mktemp]]
