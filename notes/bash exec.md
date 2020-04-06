---
tags: [bash/built-in]
title: bash exec
created: '2019-07-30T06:19:49.006Z'
modified: '2020-03-25T08:24:13.110Z'
---

# bash exec

> execute a command that completely replaces the current process. The current shell process is destroyed, and entirely replaced by the command you specify

- replace shell with command
- shell-`PID` == command-`PID`
- `echo $$ == /proc/self`
- spawns new proc

## usage
```sh
exec

exec <filename    # redirects stdin to a file - from that point on, all stdin comes from that file, rather than keyboard input 
                  # provides a method of reading a file line by line and possibly parsing each line of input using sed and/or awk

exec 3< file      # open file for reading `<` on file descriptor `3`
read -u 3 foo     # can be `read` with -u


exec >filename    # redirects stdout to a file - sends all command output that would normally go to stdout to that file

exec N > filename # affects the entire script or current shell. Redirection in the PID of the script or shell from that point on has changed. 
# However . . .
N > filename      # affects only the newly-forked process, not the entire script or shell

```

## see also
- [[bash eval]]
- [[bash read]]
