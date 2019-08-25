---
tags: [linux]
title: mount
created: '2019-07-30T06:19:49.179Z'
modified: '2019-08-21T10:57:58.648Z'
---

# mount

[[docker volume]]

### mount nfs4
```sh
mount -v -t nfs4 \
  -o nfsvers=4,rw,async \
  10.32.23.10:/nfs-server \
  /var/lib/nfs/data
```
