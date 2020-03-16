---
tags: [linux]
title: linuxkit
created: '2019-07-30T06:19:49.164Z'
modified: '2020-03-12T13:55:04.471Z'
---

# linuxkit

> toolkit for building custom minimal, immutable Linux distributions

## install
`brew tap linuxkit/linuxkit && brew install --HEAD linuxkit`

## usage
```sh
linuxkit build -format iso-bios -name kitiso minimal.yml

./linuxkit run vbox --iso kitiso.iso      # run in virtualbox
```
## see also
- [[rtf]]
- [[docker]]
- [[container]]
- [[containerd]]
- [[ctr]]
- [github.com/docker/infrakit](https://github.com/docker/infrakit)
- [github.com/linuxkit/linuxkit](https://github.com/linuxkit/linuxkit)
- [collabnix.com/top-10-reasons-why-linuxkit-is-better](http://collabnix.com/top-10-reasons-why-linuxkit-is-better-than-the-traditional-os-distribution)
