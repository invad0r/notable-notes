---
tags: [linux]
title: dd
created: '2019-07-30T06:19:49.033Z'
modified: '2019-08-22T09:33:05.499Z'
---

# dd

`disk dump`

```sh
dd if=/dev/zero of=/Users/user/filesize/foo.dat bs=1m count=24

# bs=n     Set both input and output block size to n bytes
# count=n  Copy only n input blocks

# 24+0 records in
# 24+0 records out
# 25165824 bytes transferred in 0.026832 secs (937899773 bytes/sec)
```



## i/o performance testing

```sh
dd if=/dev/zero of=/data/$(date +"%m-%d-%y_%H-%M").test bs=1G count=1 oflag=direct

# 1+0 records in
# 1+0 records out
# 1073741824 bytes (1.1 GB, 1.0 GiB) copied, 1.94133 s, 553 MB/s
```

```sh
oflag=direct # use direct I/O for data          allowed to make use of kernel buffering (it just causes a flush+wait for completion periodically
oflag=dsync  # use synchronized I/O for data    trust that all my parameters are sensible and turn off as much kernel buffering as you can"
oflag=sync   # likewise, but also for metadata
```

## see also
- [OSX illegal numeric value](https://rendezvouswithpavan.wordpress.com/2015/06/16/dd-bs-illegal-numeric-value-error-on-mac-os-x/)
- [Linux I/O Performance Tests using dd - Thomas-Krenn-Wiki](https://www.thomas-krenn.com/en/wiki/Linux_I/O_Performance_Tests_using_dd)
- [linux - why is dd with direct flag much slower than dsync - Stack Overflow](https://stackoverflow.com/a/50882704/2087704)
