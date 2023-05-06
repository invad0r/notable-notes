---
tags: [container]
title: skopeo
created: '2021-10-19T11:25:30.764Z'
modified: '2023-04-24T08:05:06.507Z'
---

# skopeo

> performs various operations on container images and image repositories

## install

```sh
brew install skopeo
```

## usage

```sh
skopeo login quay.io --username USERNAME

skopeo inspect docker://quay.io/PATH/IMAGE:TAG
```

## see also

- [[podman]]
- [[buildah]]
- [[crictl]]
- [[crane]]
- [[pack]]
