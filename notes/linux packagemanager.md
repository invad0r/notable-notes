---
tags: [linux]
title: linux packagemanager
created: '2019-07-30T06:19:49.268Z'
modified: '2019-08-02T07:39:15.249Z'
---

# linux packagemanager

✓

| comment | alpine | suse | ubuntu | redhat |
|--|--|--|--|--|
| list installed packages | `apk info`  | `yum list installed` | `apt list --installed` | `rpm -qa` |
| list available packages | `apk ..`    | `yum list available` | | |
| install package         | `apk add pkg ` | `yum install pkg` | `apt install pkg` | `rpm -i pkg` |
| uninstall package       | `apk del pkg ` | `yum remove pkg`  | `apt remove pkg`  | `rpm -e pkg` |

