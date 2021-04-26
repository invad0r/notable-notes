---
tags: [linux]
title: kill
created: '2020-01-21T09:41:17.492Z'
modified: '2021-03-25T14:54:45.667Z'
---

# kill

> send signal to a only process - contrast to [[bash kill]] which also kills [[bash jobs]]

## usage
```sh
/bin/kill -l      # list signal-name and signal-code
HUP INT QUIT ILL TRAP ABRT EMT FPE KILL BUS SEGV SYS PIPE ALRM TERM URG
STOP TSTP CONT CHLD TTIN TTOU IO XCPU XFSZ VTALRM PROF WINCH INFO USR1 USR2

/bin/kill -l 15        # prints: TERM
/bin/kill -l TERM      # prints: 15

/bin/kill -signal_name PID

/bin/kill -signal_number PID
```

## see also
- [[bash kill]]
- [[signal]]
- [[pkill]]
- [[ps]]
- [linux.die.net/man/2/kill](https://linux.die.net/man/2/kill)

