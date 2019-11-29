---
tags: [linux, packagemanager]
title: yum
created: '2019-07-30T20:38:53.233Z'
modified: '2019-09-17T12:00:00.902Z'
---

# yum

> `yellowdog updater, modified`

## usage
```sh
yum install -y package

yum install -q package
```

## find out package
```sh
yum provides $(which ip)

yum whatprovides */mkpasswd
```

## repository
```sh
yum makecache fast  # Download yum repository data to cache
```

## see also
- [[packagemanagers]]
- [[tdnf]]
- [readhat.com/yum-cheat-sheet](https://access.redhat.com/articles/yum-cheat-sheet)
- https://access.redhat.com/sites/default/files/attachments/rh_yum_cheatsheet_1214_jcs_print-1.pdf

