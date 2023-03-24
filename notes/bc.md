---
tags: [shell]
title: bc
created: '2019-09-24T06:25:36.082Z'
modified: '2023-03-22T09:48:39.898Z'
---

# bc

> `basic calculator` is an `arbitrary-precision calculator language`

## flags

```sh
-l, --mathlib       # uses the predefined math routines
```

## usage

```sh
echo "(2/3)+(7/8)"         | bc -l  # 1.54166666666666666666
echo "(2/3)+(7/8)"         | bc     # 0


echo "3.4+7/8-(5.94*3.14)" | bc     # -15.25

echo "2/3"                 | bc     # 0

echo "scale=2; 2/3"        | bc     # .66

echo "scale=2;(2/3)+(7/8)" | bc     # 1.53

echo "scale=4;(2/3)+(7/8)" | bc     # 1.5416

echo "scale=6;(2/3)+(7/8)" | bc     # 1.541666
```

## see also

- [[bash arithmetic expansion]]
- [[expr]]
- [[bash printf]]
- [[bash let]]
- [[math]]
