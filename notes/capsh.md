---
tags: [container, linux]
title: capsh
created: '2020-01-15T09:24:40.443Z'
modified: '2020-08-31T09:34:13.641Z'
---

# capsh

> capability shell wrapper

## usage

```sh
capsh --print

capsh \
  --caps="cap_net_raw+eip cap_setpcap,cap_setuid,cap_setgid+ep" \
  --keep=1 \
  --user=foo \
  --addamb=cap_net_raw \
  --print \
  --

capsh \
  --caps="cap_net_raw+eip cap_setpcap,cap_setuid,cap_setgid+ep" \
  --keep=1 \
  --user=nobody \
  --addamb=cap_net_raw \
  -- \
  -c "./ping -c1 127.0.0.1"
```

## see also

- [[capabilities]]
- [[getcap]]
