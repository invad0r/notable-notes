---
tags: [linux]
title: ls
created: '2019-07-30T06:19:49.165Z'
modified: '2019-07-30T08:44:12.306Z'
---

# ls

### directories as plaintext no rec. search
```sh
ls -d .*	                      # list only .dotfiles and .dotdirs

ls -d */                          # only directories
```

### list
```sh
ls -l | grep "^d"                 # list only directories

ls -l --ignore=*.gz --ignore=*.1  # ignore extensions
```

```
file mode printed under the -l option consists of
entry-type, owner permissions, and group permissions.

The entry type character describes the type of file:

  b     Block special file.
  c     Character special file.
  d     Directory.
  l     Symbolic link.
  s     Socket link.
  p     FIFO.
  -     Regular file.
```

### sort
```sh
ls -r         # reverse sortz
ls -S         # sort by size
ls -t         # sort by date
```
