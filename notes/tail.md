---
tags: [linux]
title: tail
created: '2019-08-21T06:27:52.472Z'
modified: '2019-11-15T07:00:15.694Z'
---

# tail

> Print last 10 lines of each FILE (or stdin) to stdout. With more than one FILE, precede each with a filename header.

## usage
```sh
tail -f file.log    # follow incoming lines


tail -n
#  -n N[kbm]       Print last N lines
#  -n +N[kbm]      Start on Nth line and print the rest


  -q              Never print headers
  -s SECONDS      Wait SECONDS between reads with -f
  -v              Always print headers
  -F              Same as -f, but keep retrying
```

## see also
- [[head]]
