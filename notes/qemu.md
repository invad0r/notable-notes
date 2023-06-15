---
tags: [virtualization]
title: qemu
created: '2020-03-13T12:51:22.771Z'
modified: '2023-05-30T07:42:39.503Z'
---

# qemu

> generic and open source machine emulator and virtualizer

## install

```sh
brew install qemu
```

## usage

```sh
sudo qemu-system-x86_64 -boot d -cdrom ./boot2docker.iso -m 512
```

## see also

- [[lima]], [[colima]]
- [[vboxmanage]]
- [[vagrant]]
- [[hyperkit]]
- [qemu.org/docs](https://www.qemu.org/docs/master/system/index.html)
