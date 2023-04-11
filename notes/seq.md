---
tags: [coreutils]
title: seq
created: '2019-07-30T06:19:49.229Z'
modified: '2023-03-13T09:21:51.496Z'
---

# seq

> print sequences of numbers

## option

```sh
-f FRMT,  --format FRMT        # printf(3) style format Only the %A, %a, %E, %e, %F, %f, %G, %g are valid
-s SEP,   --separator SEP
-t TER,   --terminator TER
-w,       --fixed-width        # equalize the widths of all numbers by padding with zeros as necessary.
```

## usage

```sh
seq 1 10                            # print 1 to 10

seq 5 2                             # print 5 to 2

seq -w 0 .05 .1                     # equalize widths of numbers by padding with zeros

seq -s '*' 40 | tr -dc '[*\n]'
```

## see also

- [[bash for]]
- [[bash printf]]
- [[tr]]
