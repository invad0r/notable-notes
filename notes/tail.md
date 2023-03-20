---
tags: [coreutils]
title: tail
created: '2019-08-21T06:27:52.472Z'
modified: '2023-03-16T13:39:17.500Z'
---

# tail

> print last 10 lines of FILE or `stdin` to `stdout`, with more than one FILE, precede each with a filename header

## flag

```sh
-q                # never print headers
-s SECONDS        # wait SECONDS between reads with -f
-v                # always print headers
-F                # same as -f, but keep retrying
-n N[kbm]         # print last N lines
-n +N[kbm]        # start on Nth line and print the rest
```

## usage

```sh
tail -f LOG.log    # follow incoming lines


tail -n 10 FILE     # print last 10 lines
```

## see also

- [[less]]
- [[head]]
- [[watch]]
