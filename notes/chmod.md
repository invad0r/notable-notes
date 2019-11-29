---
tags: [linux, osx]
title: chmod
created: '2019-10-04T09:17:53.956Z'
modified: '2019-10-18T08:23:57.033Z'
---

# chmod

## usage
```sh
_ rwx rwx rwx [int] owner:group
^               ^
|               |
|               number of hardlinks
special permissions flag
    |
    _ = no special permissions
    d = directory
    l = file or dir as symlink
    s = setuid/set guid => run executable as owner with owner permissions
    t = sticky bit
```
```sh
chmod [u|g][+|-][r|w|x]
      |       |     ^
      |       |     |
      |       |     read write execute
      |       add or remove
      user or group
```

```sh
chmod 755 file

chmod 644 dir

chmod -R 644 ./dir
```

## see also
- [[ls]]
- [[lsattr]]
- [[chattr]]
- [[filesystem]]
