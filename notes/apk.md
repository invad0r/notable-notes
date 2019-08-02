---
tags: [container/docker, linux]
title: apk
created: '2019-07-30T20:26:52.476Z'
modified: '2019-08-02T07:39:15.243Z'
---

# apk

> Software packages for `Alpine Linux` are digitally signed `tar.gz` archives containing programs, configuration files, and dependency metadata. They have the extension `.apk`, and are often called `"a-packs"`

[wiki.alpinelinux.org](https://wiki.alpinelinux.org/wiki/Alpine_Linux_package_management)

## list installed
```sh
apk info
```

## install package
```sh
apk add --no-cache package
```

### unsatisfiable constraints
if package is only available in edge alpine repo, not in a stable one
```sh
echo "http://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories
```
[docker - ERROR: unsatisfiable constraints using apk in dockerfile - Stack Overflow](https://stackoverflow.com/a/48893148)


---


[docker-alpine :: viewdocs.io](http://gliderlabs.viewdocs.io/docker-alpine/)
[BusyBox - The Swiss Army Knife of Embedded Linux](https://busybox.net/downloads/BusyBox.html)


