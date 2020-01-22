---
tags: [container, container/docker]
title: docker-machine
created: '2019-07-30T06:19:49.044Z'
modified: '2020-01-21T10:12:52.083Z'
---

# docker-machine

>  tool that lets you install Docker Engine on virtual hosts, and manage the hosts

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
- [[docker]]
