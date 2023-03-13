---
title: jsonnet
created: '2021-11-13T09:43:01.973Z'
modified: '2022-12-02T10:56:07.827Z'
---

# jsonnet

## install

```sh
brew install jsonnet
```

## usage

```sh
jsonnet -e '{ x: 1 , y: self.x + 1 } { x: 10 }'     # eval a snippet
```

## see also

- [[jq]]
- [[jo]]
- [[kustomize]]
- [[helm]]
- [jsonnet.org](https://jsonnet.org/)

