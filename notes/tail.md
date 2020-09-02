---
tags: [coreutils]
title: tail
created: '2019-08-21T06:27:52.472Z'
modified: '2020-09-01T12:46:31.376Z'
---

# tail

> print last 10 lines of FILE or `stdin` to `stdout`
> with more than one FILE, precede each with a filename header

## usage
```sh
# flags
#   -q              Never print headers
#   -s SECONDS      Wait SECONDS between reads with -f
#   -v              Always print headers
#   -F              Same as -f, but keep retrying
#   -n N[kbm]       Print last N lines
#   -n +N[kbm]      Start on Nth line and print the rest

tail -f LOG.log    # follow incoming lines


tail -n 10 FILE     # print last 10 lines
```

## see also
- [[head]]
- [[watch]]
