---
tags: [linux, packagemanager]
title: packagemanagers
created: '2019-07-30T06:19:49.268Z'
modified: '2019-09-06T06:26:36.836Z'
---

# packagemanagers

| linux manager  | list installed         | list available       | install pkg       | uninstall pkg    |
|--              |--                      |--                    |--                 |--                |
| alpine         | `apk info`             |                      | `apk add pkg`     | `apk del pkg`    |
| suse           | `yum list installed`   | `yum list available` | `yum install pkg` | `yum remove pkg` |
| ubuntu         | `apt list --installed` |                      | `apt install pkg` | `apt remove pkg` |
| redhat         | `rpm -qa`              |                      | `rpm -i pkg`      | `rpm -e pkg`     |

## see also
- [[apk]]
- [[yum]]
- [[apt]]
- [[rpm]]
- [[dpkg]]
