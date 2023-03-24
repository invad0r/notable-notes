---
tags: [container]
title: kubebuilder
created: '2021-10-19T09:45:28.946Z'
modified: '2023-03-22T10:10:46.231Z'
---

# kubebuilder

>

## install

```sh
curl -L -o kubebuilder https://go.kubebuilder.io/dl/latest/$(go env GOOS)/$(go env GOARCH)
chmod +x kubebuilder && mv kubebuilder /usr/local/bin/
```

## usage

```sh
kubebuilder create api --group webapp --version v1 --kind Guestbook
```

## see also

- [book.kubebuilder.io](https://book.kubebuilder.io/)
- [[operator-sdk]]
- [[kubectl]]
- [[kustomize]]
- [[helm]]
