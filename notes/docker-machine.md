---
tags: [container, container/docker]
title: docker-machine
created: '2019-07-30T06:19:49.044Z'
modified: '2019-08-18T15:15:36.940Z'
---

# docker-machine

### quick install
```sh
curl -L https://github.com/docker/machine/releases/download/v0.14.0/docker-machine-$(uname -s)-$(uname -m)
```

### create on virtualbox

```sh
docker-machine create -d virtualbox \
  --virtualbox-boot2docker-url file:///Users/user/boot2docker.iso \
  --virtualbox-disk-size=10000 \
  --virtualbox-memory=1024 \
  --engine-opt bip=10.32.254.1/24 \
  --engine-insecure-registry docker-registry.domain.net \
  --engine-insecure-registry dregistry.domain.net:5000 \
  somehost
```
