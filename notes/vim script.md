---
tags: [vim]
title: vim script
created: '2019-07-30T06:19:49.260Z'
modified: '2019-07-30T06:24:37.669Z'
---

# vim script
```sh
:for i in range(2016,2020)
:  for j in range(1,12)
:    let s = printf("%s-%02d-01;002000,0;00011,111", i, j)
:    put = s
:    endfor
:  endfor
```

```sh
:for i in range(2016,2020)
:  for j in range(1,12)
:    let s = printf("%s-%02d-01;002000,0;00011,111", i, j)
:    put = s
:    endfor
:  endfor
```
