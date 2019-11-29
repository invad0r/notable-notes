---
tags: [container, container/docker]
title: docker-machine
created: '2019-07-30T06:19:49.044Z'
modified: '2019-11-15T06:43:09.924Z'
---

# docker-machine

## usage
```sh
# create on virtualbox
docker-machine create \
  -d virtualbox \                                 
  --virtualbox-boot2docker-url file:///home/boot2docker.iso \
  --virtualbox-disk-size=10000 \
  --virtualbox-memory=1024 \
  --engine-opt bip=10.20.30.40/24 \
  --engine-insecure-registry HOST:PORT \
  HOST
```

## see also
- 
