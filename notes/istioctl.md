---
tags: [container]
title: istioctl
created: '2023-04-24T08:21:24.730Z'
modified: '2023-05-17T07:30:30.728Z'
---

# istioctl

> config cli utility for service operators to debug and diagnose istio [[servicemesh]]

## install

```sh
brew install istioctl

# download istoctl and example conf to current dir
curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.17.2 TARGET_ARCH=x86_64 sh -
```

## usage

```sh
istioctl install --set profile=demo -y

istioctl analyze
```

## see also

- [[crc]]
- [[minikube]]
