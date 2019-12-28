---
tags: [linux]
title: findmnt
created: '2019-10-17T05:41:04.763Z'
modified: '2019-12-09T09:59:50.299Z'
---

# findmnt

> find a filesystem 

## usage
```sh
findmnt -l    # list view 

findmnt -t nfs  # list nfs mounts

findmnt -it nfs # invert search => no nfs 

  #  -t, --types <list>     limit the set of filesystems by FS types

findmnt -l -o target,source  

  #  -o, --output <list>    the output columns to be shown
```

## see also
- [[mount]]
