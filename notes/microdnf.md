---
title: microdnf
created: '2022-09-30T12:49:43.050Z'
modified: '2023-03-16T08:02:56.188Z'
---

# microdnf

> minimal dnf for containers that uses libdnf and hence doesn't require python

## install

## usage

```sh
microdnf update

microdnf install PAGE 

microdnf install nc \
  sudo \
  iputils \
  hostname \
  findutils \
  procps

microdnf clean all
```

## see also

- [[tdnf]]
- [[yum]]
- [[rpm]]
- [[apt-get]]
