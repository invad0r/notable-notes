---
tags: [coreutils, macos]
title: cp
created: '2020-08-03T12:02:25.389Z'
modified: '2020-09-01T12:43:12.269Z'
---

# cp

> copy files

## usage
```sh
cp foo bar                # make a copy of file foo named bar

cp *.txt /tmp             # copy group of files to dir
    
cp -R DIR /tmp           # copy the dir (including subdirectories) to the /tmp dir

cp --update SOURCE DEST   # copy only when the SOURCE file is newer than the DEST file or when the DEST file is missing
```
## see also
- [[mv]]
- [[pbcopy pbpaste]]
- [[rsync]]
