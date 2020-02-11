---
tags: [linux, packagemanager]
title: yum
created: '2019-07-30T20:38:53.233Z'
modified: '2020-02-03T12:28:39.380Z'
---

# yum

> `yellowdog updater, modified`

## usage
```sh
yum install -y package

yum install -q package

yum remove pkg


yum provides $(which ip)        # find out package

yum whatprovides */mkpasswd     # find out package


yum makecache fast  # Download yum repository data to cache

yum list installed

yum list available
```

## see also
- [[rpm]]
- [[tdnf]]
- [readhat.com/yum-cheat-sheet](https://access.redhat.com/articles/yum-cheat-sheet)
- https://access.redhat.com/sites/default/files/attachments/rh_yum_cheatsheet_1214_jcs_print-1.pdf

