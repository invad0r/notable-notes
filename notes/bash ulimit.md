---
tags: [container, shell/bash/builtin]
title: bash ulimit
created: '2019-08-02T06:42:37.646Z'
modified: '2023-03-22T10:03:05.385Z'
---

# bash ulimit

> provides control over the resources available to the shell and processes it creates, on systems that allow such control

## option

```sh
-S        # use the `soft` resource limit
-H        # use the `hard` resource limit

-a        # all current limits are reported
-b        # socket buffer size
-c        # maximum size of core files created
-d        # maximum size of a process's data segment
-e        # maximum scheduling priority (`nice')
-f        # maximum size of files written by the shell and its children
-i        # maximum number of pending signals
-l        # maximum size a process may lock into memory
-m        # maximum resident set size
-n        # maximum number of open file descriptors
-p        # pipe buffer size
-q        # maximum number of bytes in POSIX message queues
-r        # maximum real-time scheduling priority
-s        # maximum stack size
-t        # maximum amount of cpu time in seconds
-u        # maximum number of user processes
-v        # size of virtual memory
-x        # maximum number of file locks
```

## usage

```sh
ulimit -a       # show all ulimits

ulimit -nH      # check hard limit for filedescriptors
ulimit -nS     # check soft limit for filedescriptors

ulimit -u       # max num of processes user can start
ulimit -uH      # hard limit of processes user can start
ulimit -uS      # soft limit of processes user can start

ulimit -c       # filesize for core-dumps; default=0

ulimit -l       # max locked memory (kbytes)
                #   memlock see docker-compose
                #   memlock:  locks sets of pages in memory => jvm-gc goes thorugh all pages of Heap !
                #   mlockall: lock all pages
```

## see alos

- [[sysctl]]
- [[systemctl]]
- [[nproc]]
- [[docker-compose]]
- [[elasticsearch]]
