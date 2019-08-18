---
tags: [linux]
title: lsof
created: '2019-07-30T06:19:49.166Z'
modified: '2019-08-18T14:40:52.836Z'
---

# lsof

`list open files`

## open ports

```sh
-P  # don't convert port-number to port-name


lsof -Pi :PORT

lsof -iTCP
lsof -iUDP

lsof -i4
lsof -i6
```
