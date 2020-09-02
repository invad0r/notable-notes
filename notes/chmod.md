---
tags: [coreutils, macos]
title: chmod
created: '2019-10-04T09:17:53.956Z'
modified: '2020-09-01T12:43:12.239Z'
---

# chmod

> change file modes or Access Control Lists

## usage
```sh
chmod 755 file

chmod 644 dir

chmod -R 644 ./dir

#  chmod [u|g][+|-][r|w|x]
#        |       |     ^
#        |       |     |
#        |       |     read write execute
#        |       add or remove
#      user or group
#
#  _ rwx rwx rwx [int] owner:group
#  ^               ^
#  |               |
#  |               number of hardlinks
#  special permissions flag
#      |
#      _   no special permissions
#      d   directory
#      l   file or dir as symlink
#      s   setuid/set guid => run executable as owner with owner permissions
#      t   sticky bit
#  
```

## see also
- [[chown]]
- [[ls]]
- [[lsattr]]
- [[chattr]]
- [[filesystem]]
