---
title: ulimit
created: '2020-02-14T12:04:23.494Z'
modified: '2020-02-17T11:35:05.919Z'
---

# ulimit

## usage
```sh
ulimit -a       # show all ulimits

ulimit -u       # max num of processes user can start

ulimit -u -H    # hard limit
ulimit -u -S    # soft limit

ulimit -c       # filesize for core-dumps; default=0

ulimit -l       # max locked memory (kbytes)
                #   memlock see docker-compose
                #   memlock:  locks sets of pages in memory => jvm-gc goes thorugh all pages of Heap !
                #   mlockall: lock all pages
```

## see alos
- [[sysctl]]
- [[nproc]]
- [[docker-compose]]
- [[elasticsearch]]
