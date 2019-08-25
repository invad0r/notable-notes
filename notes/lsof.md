---
tags: [linux]
title: lsof
created: '2019-07-30T06:19:49.166Z'
modified: '2019-08-21T09:03:41.258Z'
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

### ignore warnings

```sh
lsof: no pwd entry for UID 100

lsof -w     # ignore warnings
```
[lsof-no-pwd-entry-for-uid](https://unix.stackexchange.com/a/193920/193945)
