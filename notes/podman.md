---
tags: [container]
title: podman
created: '2021-09-06T12:17:24.319Z'
modified: '2021-10-29T12:38:12.982Z'
---

# podman

## install

`brew install podman`

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
