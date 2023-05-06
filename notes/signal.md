---
tags: [linux, Notebooks]
title: signal
created: '2020-01-21T09:37:12.241Z'
modified: '2023-05-05T07:07:35.739Z'
---

# signal

> signals are a limited form of `ipc` used in Unix-like and POSIX-compliant os
> a signal is a asynchronous notification sent to a process/thread within the same process in order to notify it of an event that occurred

## standard signals POSIX.1-1990
 
```sh
signal      value         action    comment
---         ---           ---       ---
SIGHUP      1             Term      Hangup detected on controlling terminal or death of controlling process
SIGINT      2             Term      Interrupt from keyboard
SIGQUIT     3             Core      Quit from keyboard
SIGILL      4             Core      Illegal Instruction
SIGABRT     6             Core      Abort signal from abort(3)
SIGFPE      8             Core      Floating point exception
SIGKILL     9             Term      Kill signal
SIGSEGV     11            Core      Invalid memory reference
SIGPIPE     13            Term      Broken pipe: write to pipe with no readers
SIGALRM     14            Term      Timer signal from alarm(2)
SIGTERM     15            Term      Termination signal
SIGUSR1     30, 10, 16    Term      User-defined signal 1
SIGUSR2     31, 12, 17    Term      User-defined signal 2
SIGCHLD     20, 17, 18    Ign       Child stopped or terminated
SIGCONT     19, 18, 25    Cont      Continue if stopped
SIGSTOP     17, 19, 23    Stop      Stop process
SIGTSTP     18, 20, 24    Stop      Stop typed at terminal
SIGTTIN     21, 21, 26    Stop      Terminal input for background process
SIGTTOU     22, 22, 27    Stop      Terminal output for background process

SIGKILL and SIGSTOP cannot be caught, blocked, or ignored
```

## usage

```sh
kill -l     # list signals
```

## see also

- [[syscall]]
- [[kill]]
- [[bash kill]]
- [[bash trap]]
- [[errno]]
- [[nohup]]
- [[c stackoverflow segfault]]
- [[12 factor app]]
- [linux.die.net/man/7/signal](https://linux.die.net/man/7/signal)
