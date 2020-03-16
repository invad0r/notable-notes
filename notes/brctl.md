---
tags: [linux, network]
title: brctl
created: '2019-08-28T12:22:49.494Z'
modified: '2020-03-12T14:06:23.474Z'
---

# brctl

> `brctl` ethernet bridge administration is used to set up, maintain, and inspect the ethernet bridge configuration in the linux kernel

## install 
`yum install bridge-utils -y`

## usage
```sh
ip add show docker0

brctl show docker0
```

## see also
- [[docker network]]
- [[ip]]

