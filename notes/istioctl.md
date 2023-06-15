---
tags: [container]
title: istioctl
created: '2023-04-24T08:21:24.730Z'
modified: '2023-05-23T08:16:33.750Z'
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

istioctl dashboard envoy deployment/productpage-v1
istioctl dash      envoy productpage-123-456.default
istioctl d         envoy productpage-123-456.default
```

## see also

- [[crc]]
- [[minikube]]
