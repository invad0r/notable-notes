---
tags: [filesystem]
title: xfs_repair
created: '2020-01-07T10:05:34.393Z'
modified: '2020-01-07T10:13:56.127Z'
---

# xfs_repair

> repair corrupt or damaged xfs filesystem

## usage
```sh
xfs_repair -V

umount /dev/sda2

xfs_repair /dev/sda2
```
## see also
- [[xfs]]
- [[xfs_info]]
- [[xfs_growfs]]
- http://nerdbynature.de/s9y/2016/05/06/XFS-Corruption-warning-Metadata-has-LSN-ahead-of-current-LSN
- [Corruption warning: Metadata has LSN (6:49052) ahead of current LSN](https://microdevsys.com/wp/corruption-warning-metadata-has-lsn-649052-ahead-of-current-lsn-649006-please-unmount-and-run-xfs_repair-v4-3-to-resolve/)
