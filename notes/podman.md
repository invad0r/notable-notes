---
tags: [container]
title: podman
created: '2021-09-06T12:17:24.319Z'
modified: '2023-03-22T11:11:54.370Z'
---

# podman

## install

```sh
brew install podman
```

## usage

```sh
podman machine init

podman machine start

podman machine list

podman machine ssh


podman build -t TAG .

podman run -ti --rm IMAGE
```

## see also

- [[docker]]
- [[skopeo]]
