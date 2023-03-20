---
title: kind
created: '2021-11-29T09:47:11.585Z'
modified: '2023-03-17T07:20:16.723Z'
---

# kind

> run local kubernetes clusters using [[docker]] container "nodes"

## install

```sh
brew install kind
```

## usage

```sh
kind create cluster --image=kindest/node:v1.22.4 --config CONFIG.yaml

kind get clusters

kind delete cluster --name NAME
 
kind load docker-image my-custom-image-0 my-custom-image-1 --name NAME    # images can be loaded into your cluster nodes
```

## see also

- [[k3s]]
- [[kubectl]]
- [[minikube]]
- [[docker]]
- [kind.sigs.k8s.io/](https://kind.sigs.k8s.io/)
