---
tags: [linux]
title: findmnt
created: '2019-10-17T05:41:04.763Z'
modified: '2020-01-07T07:46:50.116Z'
---

# findmnt

> find a filesystem 

## usage
```sh
findmnt -l            # list view 

findmnt -t nfs        # list nfs mounts

findmnt -it nfs,tmpfs,overlay,nsfs,cgroup,proc       # invert search => no nfs, tmpfs, overlay ..

  #  -t, --types <list>     limit the set of filesystems by FS types

findmnt -l -o target,source  

  #  -o, --output <list>    the output columns to be shown
```

## see also
- [[mount]]
