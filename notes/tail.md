---
tags: [coreutils]
title: tail
created: '2019-08-21T06:27:52.472Z'
modified: '2022-02-01T15:14:45.673Z'
---

# tail

> print last 10 lines of FILE or `stdin` to `stdout`, with more than one FILE, precede each with a filename header

## usage

```sh
-q                # never print headers
-s SECONDS        # wait SECONDS between reads with -f
-v                # always print headers
-F                # same as -f, but keep retrying
-n N[kbm]         # print last N lines
-n +N[kbm]        # start on Nth line and print the rest
```

```sh
tail -f LOG.log    # follow incoming lines


tail -n 10 FILE     # print last 10 lines
```

## see also

- [[less]]
- [[head]]
- [[watch]]
