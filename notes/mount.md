---
tags: [linux]
title: mount
created: '2019-07-30T06:19:49.179Z'
modified: '2019-08-18T14:38:47.024Z'
---

# mount


### mount nfs4
```sh
mount -v -t nfs4 \
  -o nfsvers=4,rw,async \
  10.32.23.10:/nfs-server \
  /var/lib/nfs/data
```
