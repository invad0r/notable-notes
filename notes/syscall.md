---
tags: [linux, macos]
title: syscall
created: '2023-05-05T06:54:04.664Z'
modified: '2023-05-05T07:12:44.300Z'
---

# syscall

## usage

```sh
creat(2)                    # create a new file
access(2), faccessat(2)     # check accessibility of a file
clonefile(2)                # create copy on write clones of files
open(2), openat(2)          # open or create a file for reading or writing
exchangedata(2)             # atomically exchange data between two files
fcntl(2)                    # file control
fhopen(2)                   # open a file by file handle
flock(2)                    # apply or remove an advisory lock on an open file
getfh(2)                    # get file handle
fstat(2), fstat64(2), ..    # get file status
fsync(2)                    # synchronize a file's in-core state with that on disk
ftruncate(2), truncate(2)   # truncate or extend a file to a specified length
futimes(2), utimes(2)       # set file access and modification times
lseek(2)                    # reposition read/write file offset
mknod(2)                    # make a special file node
rename(2), renameat(2), ..  # change the name of a file
revoke(2)                   # revoke file access
sync(2)                     # synchronize disk block in-core status with that on disk
umask(2)                    # set file creation mode mask
undelete(2)                 # attempt to recover a deleted file
```

## see also

- [[c]]
- [[man]]
- [[strace]]
- [[signal]]
