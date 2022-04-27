---
tags: [linux, macos]
title: install
created: '2019-09-25T07:09:47.701Z'
modified: '2022-04-06T08:37:58.499Z'
---

# install

> copy files and set attributes, but also change ownership/permissions and remove debugging symbols from executables

## flags

```sh
-g, --group=GROUP               # set group ownership, instead of process' current group
-m, --mode=MODE                 # set permission mode (as in chmod), instead of rwxr-xr-x
-o, --owner=OWNER               # set ownership (super-user only)
-p, --preserve-timestamps       # apply access/modification times of SOURCE to corresponding DEST files
```

## usage

```sh
install -D /SOURCE/DIR/*.py /DESTINATION/DIR

install -d /DESTINATION/DIR

install -m 0755 -d DIR
install -m 0755 FILE DIR/FILE

install -m 0755 -d DIR/man1
install -m 0644 FILE.1 DIR/man1/FILE.1
```

## see also

- [[chmod]]
- [[mv]]
- [[make]]
- [ss64.com/bash/install.html](https://ss64.com/bash/install.html)
