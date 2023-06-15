---
tags: [container, linux, macos, virtualization]
title: colima
created: '2023-05-30T07:23:59.486Z'
modified: '2023-05-30T07:42:57.492Z'
---

# colima

> containers in [[lim]] - container runtimes on macoss (and Linux) with minimal setup

## install

```sh
brew install colima
```

## option

```sh
-h, --help                # help for colima
-p, --profile PROFILE     # profile name, for multiple instances (default "default")
-v, --verbose             # enable verbose log
    --version             # version for colima
    --very-verbose        # enable more verbose log
```

## usage

```sh
colima completion         # generate completion script
colima delete             # delete and teardown Colima
colima help               # help about any command
colima kubernetes         # manage Kubernetes cluster
colima list               # list instances
colima nerdctl            # run nerdctl (requires containerd runtime)
colima restart            # restart Colima
colima ssh                # SSH into the VM
colima ssh-config         # show SSH connection config

colima start              # start Colima
colima start --arch x86_64 --memory 4

colima status             # show the status of Colima
colima stop               # stop Colima
colima template           # edit the template for default configurations
colima version            # print the version of Colima
```

## see also

- [[lima]]
- [[qemu]]
- [[docker]]
- [[nerdctl]]
- [github.com/abiosoft/colima](https://github.com/abiosoft/colima)
