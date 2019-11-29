---
tags: [bash, linux]
title: expr
created: '2019-09-24T06:30:09.956Z'
modified: '2019-09-24T09:22:02.631Z'
---

# expr

> `evaluate expression` using only `integer` and tops out at `2^63 - 1`

```sh
expr 1 + 1           # = 2

myvar=$(expr 1 + 1)  # $myvar == 2

expr $myvar + 1      # = 3

expr $myvar / 3      # = 1

expr $myvar \* 3     # = 9
```

## see also
- [[bc]]
- [[expr]]
- [[bash let.md]]
- [[bash arithmetic expansion]]
