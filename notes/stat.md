---
tags: [linux]
title: stat
created: '2019-07-30T06:19:49.247Z'
modified: '2023-03-15T07:20:00.593Z'
---

# stat

> display file status

## flags

```sh
-l          # display output in ls -lT format
-n          # do not force a newline to appear at the end of each piece of output
-r          # display raw information
-s          # display information in shell output format, suitable for initializing variables
-f FORMAT   # display information using the specified format
```

## format

```sh
  k    # optimal file system I/O operation block size
  z    # size of file in bytes
  b    # number of blocks allocated for file
```

## usage

```sh
stat -f "%k, %z, %b" FILE    #  4096, 25165824, 49152 
```

## see also

- [[ls]]
- [[file]]
- [[touch]]
- [[readlink]]
- [[bash printf]]
