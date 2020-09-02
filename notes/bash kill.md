---
tags: [bash/built-in]
title: bash kill
created: '2019-08-02T06:42:37.606Z'
modified: '2020-08-25T14:52:35.812Z'
---

# bash kill

> send a signal to a job
> is a shell builtin for two reasons:  it allows job IDs to be used instead of process IDs, and allows processes to be killed if the limit on processes that you can create is reached

## usage
```sh
# send processes-identified by PID or JOBSPEC the signal named by SIGSPEC or SIGNUM
# if neither SIGSPEC nor SIGNUM is present, then SIGTERM is assumed

# options
#  -s sig    SIG is a signal name
#  -n sig    SIG is a signal number
#  -l        list the signal names; if arguments follow `-l' they are assumed to be signal numbers for which names should be listed
#  -L        synonym for -l

kill -l     # list signals

kill -signal pid

kill -1 1001        # SIGHUP

kill -9 1001        # SIGKILL
```

## see also
- [[signal]]
- [[bash jobs]]
- [[pkill]]
- [linux.die.net/man/2/kill](https://linux.die.net/man/2/kill)

