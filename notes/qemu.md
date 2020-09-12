---
tags: [virtualization]
title: qemu
created: '2020-03-13T12:51:22.771Z'
modified: '2020-09-02T18:03:54.387Z'
---

# qemu

> generic and open source machine emulator and virtualizer

## install
`brew install qemu`

## usage
```sh
sudo qemu-system-x86_64 -boot d -cdrom ./boot2docker.iso -m 512
```

## see also
- [qemu.org/docs](https://www.qemu.org/docs/master/system/index.html)
- [[vboxmanage]]
- [[vagrant]]
- [[hyperkit]]
