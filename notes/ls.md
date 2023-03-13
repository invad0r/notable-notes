---
tags: [coreutils]
title: ls
created: '2019-07-30T06:19:49.165Z'
modified: '2022-06-20T06:42:05.132Z'
---

# ls

> list directory contents

## flags

```sh
-1                 # force output to be one entry per line.
-i                 # print each file's inode number
-A                 # list all entries except for . and ..
-r                 # reverse sort

-S                 # sort by size
-t                 # sort by date

-Z, --context      # security context so it fits on most displays. displays only mode, user, group, security context and file name. aka "SELinux context"
```

## usage

```sh
ls -lisa

ls -d .*	                        # list only .dotfiles and .dotdirs

ls -d */                          # only directories
ls -l | grep "^d"                 # list only directories

ls -l --ignore=*.gz --ignore=*.1  # ignore extensions

ls -ls foo.dat
#   -s      argument to ls returns file size in blocks, just like du
#   49152 -rw-r--r--  1 user  staff  25165824  3 Jan 17:21 foo.dat

ls -l                             # prints file-mode, which consists of entry-type, owner-permissions, and group-permissions
#   d rwx r-x r-x ..
#   ┬
#  entry type character describes the type of file:
#    b     Block special file
#    c     Character special file
#    d     Directory
#    l     Symbolic link
#    s     Socket link
#    p     FIFO
#    -     Regular file
```

## see also

- [[exa]]
- [[lsattr]]
- [[chmod]]
- [[df]]
- [[find]]
- [[tree]]
- [[stat]]
