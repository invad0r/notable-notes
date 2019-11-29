---
tags: [filesystem, linux, osx]
title: ls
created: '2019-07-30T06:19:49.165Z'
modified: '2019-10-23T14:45:10.035Z'
---

# ls

> list directory contents

## usage
```sh
ls -1                             # force output to be one entry per line.

ls -A                             # list all entries except for . and ..

ls -d .*	                        # list only .dotfiles and .dotdirs

ls -d */                          # only directories

ls -l | grep "^d"                 # list only directories

ls -l --ignore=*.gz --ignore=*.1  # ignore extensions

ls -r                             # reverse sort

ls -S                             # sort by size

ls -t                             # sort by date
```

## file mode
```sh
ls -l  # prints file-mode, which consists of entry-type, owner-permissions, and group-permissions

d rwx r-x r-x ..

# The entry type character describes the type of file:
#
#  b     Block special file
#  c     Character special file
#  d     Directory
#  l     Symbolic link
#  s     Socket link
#  p     FIFO
#  -     Regular file
```

## see also
- [[lsattr]]
- [[chmod]]
- [[find]]
- [[tree]]
- [[stat]]
