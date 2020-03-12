---
tags: [linux]
title: chattr
created: '2019-10-04T09:02:35.919Z'
modified: '2020-03-03T12:52:29.948Z'
---

# chattr

> `chattr` changes the file attributes on a Linux file system.

## usage
```sh
chattr +i file    # make file imutable / read-only
chattr -i file    # remove read-only restriction

chattr +a file    # append-only
chattr -a file    # remove append-only

chattr -R +i ./dir/   # apply restriction to all files in dir

# format of a symbolic mode is +-=[aAcCdDeijsStTu]
#   +   causes  the  selected attributes to be added to the existing attributes of the files
#   -   causes them to  be  removed
#   =   causes them to be the only attributes that the files have.
# letters select the new attributes for the files:
#   a   append only
#   A   no atime updates
#   c   compressed
#   C   no copy on write
#   d   no dump
#   D   synchronous directory updates
#   e   extent format
#   i   immutable
#   j   data journalling
#   s   secure deletion 
# synchronous
#   S   updates 
#   t   no tail-merging
#   T   top of directory hierarchy
#   u   undeletable
# read-only attributes, and may be listed by lsattr but not modified by chattr
#   E   compression  error
#   h   huge file
#   I   indexed directory
#   N   inline data
#   X   compression raw access
#   Z   compressed dirty file
```

## see also
- [[lsattr]]
- [[chflags]]
- [[chmod]]
- [[btrfs]]
- [[ext4]]
- [[xfs]]
