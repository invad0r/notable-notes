---
tags: [shell/bash/builtin]
title: bash kill
created: '2019-08-02T06:42:37.606Z'
modified: '2022-04-27T14:29:12.970Z'
---

# bash kill

> send a signal to a job

- is a shell builtin for two reasons:  
  - it allows job IDs to be used instead of process IDs
  - it allows processes to be killed if the limit on processes that you can create is reached

- send processes-identified by PID or JOBSPEC the signal named by SIGSPEC or SIGNUM
- if neither SIGSPEC nor SIGNUM is present, then SIGTERM is assumed

## usage

```sh
-s SIG    # SIG is a signal name
-n SIG    # SIG is a signal number
-l        # list the signal names; if arguments follow `-l' they are assumed to be signal numbers for which names should be listed
-L        # synonym for -l
```

```sh
kill -l             # list signals

kill -signal PID

kill -1  PID         # SIGHUP
kill -9  PID         # SIGKILL
kill -15 PID         # SIGTERM
```

## see also

- [[signal]]
- [[bash jobs]]
- [[kill]]
- [[pkill]]
- [[ps]]
- [linux.die.net/man/2/kill](https://linux.die.net/man/2/kill)

