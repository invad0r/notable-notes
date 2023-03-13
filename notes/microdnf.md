---
title: microdnf
created: '2022-09-30T12:49:43.050Z'
modified: '2022-09-30T13:14:19.747Z'
---

# microdnf

> minimal dnf for containers that uses libdnf and hence doesn't require python

## install

## usage

```sh
microdnf install nc

microdnf update && microdnf install sudo iputils hostname findutils 

microdnf clean all
```

## see also

- [[tdnf]]
- [[yum]]
