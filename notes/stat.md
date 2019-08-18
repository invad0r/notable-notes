---
tags: [linux]
title: stat
created: '2019-07-30T06:19:49.247Z'
modified: '2019-07-30T08:49:30.941Z'
---

# stat



```sh
ls -ls foo.dat    # -s argument to ls returns file size in blocks, just like du
                  # 49152 -rw-r--r--  1 user  staff  25165824  3 Jan 17:21 foo.dat

echo $((25165824/1024/1024)) # 24
```

```sh
stat -f "%k, %z, %b" foo.dat
  
  # k - Optimal file system I/O operation block size.
  # z - The size of file in bytes.
  # b - Number of blocks allocated for file.
  
  # 4096, 25165824, 49152
```


