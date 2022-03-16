---
title: k0s
created: '2022-01-27T09:47:59.070Z'
modified: '2022-02-02T10:44:38.564Z'
---

# k0s

> single binary, no host OS dependencies besides the host OS kernel, all-inclusive Kubernetes distribution

## install

`curl -sSLf https://get.k0s.sh | sudo sh`

## usage

```sh
k0s --help

k0s install controller --single

k0s start

k0s kubectl get nodes

k0s stop

k0s reset
```

## see also

- [[k3s]]
- [[k9s]]
- [[k3d]]
- [docs.k0sproject.io/v1.23.1+k0s.1/](https://docs.k0sproject.io/v1.23.1+k0s.1/)
