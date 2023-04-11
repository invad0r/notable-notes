---
tags: [linux, macos]
title: time
created: '2020-09-09T08:34:51.671Z'
modified: '2023-03-24T08:23:34.433Z'
---

# time

> time utility executes and times utility.  

After the utility finishes, time writes the total time elapsed, the time consumed by system overhead, and the time used to execute utility to the standard error stream.  
Times are reported in seconds.

## option

```sh
-l      # contents of the rusage structure are printed
-p      # output is formatted as specified by IEEE Std 1003.2-1992 (``POSIX.2'')
```

## usage

```sh
/usr/bin/time CMD     # use full path or built-in `time` will be used

\time                 # use executable instead of the shell keyword though, 
                      # you can either type the full path, i.e. /usr/bin/time, 
                      # or you can prefix the command with a backslash to stop Bash from evaluating it: \time
```

## see also

- [[bash time]]
- [[bash type]]
- [[bash alias]]
