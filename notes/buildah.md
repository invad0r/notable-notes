---
tags: [buildsystem, container]
title: buildah
created: '2021-10-19T11:40:08.335Z'
modified: '2023-04-24T08:04:51.781Z'
---

# buildah


## install

```sh
yum -y install buildah
```

## usage

```sh
buildah from centos
buildah run centos-working-container yum install httpd -y
buildah copy centos-working-container index.html /var/www/html/index.html
buildah config --entrypoint "/usr/sbin/httpd -DFOREGROUND" centos-working-container
buildah commit centos-working-container redhat-website

buildah bud -t fedora-httpd     # bud = "build-using-dockerfile"

buildah images
```

## see also

- [buildah.io](https://buildah.io/)
- [[podman]]
- [[skopeo]]
- [[docker]]
- [[crictl]]
- [[pack]]

