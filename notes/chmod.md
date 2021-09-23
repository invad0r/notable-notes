---
tags: [coreutils, macos]
title: chmod
created: '2019-10-04T09:17:53.956Z'
modified: '2021-06-07T07:04:16.697Z'
---

# chmod

> change file modes or Access Control Lists

## usage
```sh
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
```
```sh
chmod 755 FILE

chmod 644 DIR

chmod -R 644 DIR

chmod g-w FILE      # remove write from group
chmod u+rw FILE     # give permission read, write to user
```

## see also
- [[chown]]
- [[ls]]
- [[lsattr]]
- [[chattr]]
- [[filesystem]]
- [[bash umask]]
