---
tags: [coreutils]
title: seq
created: '2019-07-30T06:19:49.229Z'
modified: '2020-09-01T12:43:12.475Z'
---

# seq

> print sequences of numbers

## usage
```sh
seq 1 10                            # print 1 to 10

seq 5 2                             # print 5 to 2

seq -w 0 .05 .1                     # equalize widths of numbers by padding with zeros

seq -s '*' 40 | tr -dc '[*\n]'
```

## see also
- [[bash for]]
- [[tr]]
