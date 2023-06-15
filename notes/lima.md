---
title: lima
created: '2023-05-30T07:38:10.191Z'
modified: '2023-05-31T07:43:03.406Z'
---

# lima

## install

```sh
brew install lima
```

## env

```sh
LIMA_INSTANCE            # 
LIMA_SHELL               #
LIMA_WORKDIR             # 
```

## option

```sh
lima
```

## usage

```sh
limactl start default

limactl start --name=default template://docker

limactl disk list       # list all existing disks
```

## see also

- [[colima]]
- [[qemu]]
