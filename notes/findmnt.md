---
tags: [linux]
title: findmnt
created: '2019-10-17T05:41:04.763Z'
modified: '2019-11-29T11:36:39.065Z'
---

# findmnt

> find a filesystem 

## usage
```sh
findmnt -l    # list view 

findmnt -t nfs  # list nfs mounts

  #  -t, --types <list>     limit the set of filesystems by FS types

findmnt -l -o target,source  

  #  -o, --output <list>    the output columns to be shown
```

## see also
- [[mount]]
