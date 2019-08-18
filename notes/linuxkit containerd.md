---
tags: [linux]
title: linuxkit containerd
created: '2019-07-30T06:19:49.164Z'
modified: '2019-08-18T14:42:25.357Z'
---

# linuxkit containerd

auf alpine-linux basis mit `ash``

> https://github.com/linuxkit/linuxkit
> http://collabnix.com/top-10-reasons-why-linuxkit-is-better-than-the-traditional-os-distribution


https://github.com/docker/infrakit

```sh
linuxkit build -format iso-bios -name kitiso minimal.yml
```
## run in virtualbox
```sh
./linuxkit run vbox --iso kitiso.iso
```

## containerd CLI

```st
ctr --help        # very helpful
```
```sh
ctr tasks ls    # list current running services
```

```sh
ctr contai
```
