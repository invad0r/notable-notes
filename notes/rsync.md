---
tags: [linux]
title: rsync
created: '2019-07-30T06:19:49.224Z'
modified: '2020-08-03T12:09:28.843Z'
---

# rsync

> a fast, versatile, remote (and local) file-copying tool

## usage
```sh
rsync -av host::src /dest

rsync -avz --remove-source-files user@foo.bar.baz:/home/user/backup.gz.tar .
```

## see also
- [[cp]]
- [[ssh]]
