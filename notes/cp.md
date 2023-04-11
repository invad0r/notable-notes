---
tags: [coreutils, macos]
title: cp
created: '2020-08-03T12:02:25.389Z'
modified: '2022-04-09T09:35:41.742Z'
---

# cp

> copy files

## option

```sh
-n            # do not overwrite existing file, overrides any previous -f or -i

-l            # create hard links to regular files in a hierarchy instead of copying

-R            # if source designates a dir, it copies the directory and the entire subtree connected at that point
              # if source ends in /, contents of the directory are copied rather than the directory, symbolic links are copied
```

## usage

```sh
cp foo bar                # make a copy of file foo named bar

cp *.txt /tmp             # copy group of files to dir
    
cp -R DIR /tmp           # copy the dir (including subdirectories) to the /tmp dir

cp --update SOURCE DEST   # copy only when the SOURCE file is newer than the DEST file or when the DEST file is missing
```

## see also

- [[ln]]
- [[mv]]
- [[pbcopy pbpaste]]
- [[rsync]]
