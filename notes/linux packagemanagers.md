---
tags: [linux, packagemanager]
title: linux packagemanagers
created: '2019-07-30T06:19:49.268Z'
modified: '2019-08-20T08:24:12.207Z'
---

# linux packagemanagers

| linux manager  | list installed         | list available       | install pkg       | uninstall pkg    |
|--              |--                      |--                    |--                 |--                |
| alpine [[apk]] | `apk info`             |                      | `apk add pkg`     | `apk del pkg`    |
| suse   [[yum]] | `yum list installed`   | `yum list available` | `yum install pkg` | `yum remove pkg` |
| ubuntu [[apt]] | `apt list --installed` |                      | `apt install pkg` | `apt remove pkg` |
| redhat [[rpm]] | `rpm -qa`              |                      | `rpm -i pkg`      | `rpm -e pkg`     |
