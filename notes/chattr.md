---
tags: [linux]
title: chattr
created: '2019-10-04T09:02:35.919Z'
modified: '2019-10-04T09:16:55.368Z'
---

# chattr

> `chattr` changes the file attributes on a Linux file system.

```
format of a symbolic mode is +-=[aAcCdDeijsStTu].

+     # causes  the  selected attributes to be added to the existing attributes of the files
-     # causes them to  be  removed
=     # causes them to be the only attributes that the files have.

letters select the new attributes for the files:
append only (a)
no atime updates (A)
compressed (c)
no copy on write (C)
no dump (d)
synchronous directory updates (D)
extent format (e)
immutable (i)
data journalling (j)
secure deletion  (s)
synchronous
updates  (S)
no tail-merging (t)
top of directory hierarchy (T)
undeletable (u)

The following attributes are read-only, and may be listed by  lsattr(1) but  not  modified  by  chattr: 
compression  error (E)
huge file (h)
indexed directory (I)
inline data (N)
compression raw access (X)
compressed dirty file (Z)

Not  all  flags  are supported or utilized by all filesystems; refer to
filesystem-specific man pages such as btrfs(5), ext4(5), and xfs(5)
```

## usage
```sh
chattr +i file    # make file imutable / read-only

chattr -i file    # remove read-only restriction
```
```sh
chattr +a file    # append-only

chattr -a file    # remove append-only
```

```sh
chattr -R +i ./dir/   # apply restriction to all files in dir
```

## see also
- [[lsattr]]
- [[chflags]]
- [[chmod]]
