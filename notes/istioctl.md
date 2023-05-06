---
tags: [container]
title: istioctl
created: '2023-04-24T08:21:24.730Z'
modified: '2023-05-05T06:57:31.885Z'
---

# istioctl


## install

```sh
curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.17.2 TARGET_ARCH=x86_64 sh -       # download istoctl and example conf to current dir
```

## usage

```sh
istioctl install --set profile=demo -y

istioctl analyze
```

## see also

- [[minikube]]
