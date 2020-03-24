---
tags: [linux]
title: stat
created: '2019-07-30T06:19:49.247Z'
modified: '2020-03-16T16:35:42.950Z'
---

# stat

> display file status

## usage
```sh
stat -f "%k, %z, %b" foo.dat    #  4096, 25165824, 49152 
#
#  k    Optimal file system I/O operation block size.
#  z    The size of file in bytes.
#  b    Number of blocks allocated for file.
```

## see also
- [[ls]]
- [[file]]
- [[readlink]]
