---
tags: [bash]
title: bc
created: '2019-09-24T06:25:36.082Z'
modified: '2020-09-02T18:09:51.668Z'
---

# bc

> `basic calculator` is an `arbitrary-precision calculator language`

## usage
```sh
bc -l           # -l, --mathlib: Uses the predefined math routines.

echo "3.4+7/8-(5.94*3.14)" | bc     # = -15.25

echo "2/3"                 | bc     # = 0

echo "scale=2; 2/3"        | bc     # = .66

echo "(2/3)+(7/8)"         | bc     # = 0

echo "scale=2;(2/3)+(7/8)" | bc     # = 1.53

echo "scale=4;(2/3)+(7/8)" | bc     # = 1.5416

echo "scale=6;(2/3)+(7/8)" | bc     # = 1.541666

echo "(2/3)+(7/8)"         | bc -l  # = 1.54166666666666666666
```

## see also
- [[bash arithmetic expansion]]
- [[expr]]
- [[bash printf]]
- [[bash let.md]]
