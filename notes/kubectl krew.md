---
title: kubectl krew
created: '2022-06-27T06:44:31.241Z'
modified: '2022-11-23T08:33:45.066Z'
---

# kubectl krew

> plugin manager for [[kubectl]]

## install

```sh
(
  set -x; cd "$(mktemp -d)" &&
  OS="$(uname | tr '[:upper:]' '[:lower:]')" &&
  ARCH="$(uname -m | sed -e 's/x86_64/amd64/' -e 's/\(arm\)\(64\)\?.*/\1\2/' -e 's/aarch64$/arm64/')" &&
  KREW="krew-${OS}_${ARCH}" &&
  curl -fsSLO "https://github.com/kubernetes-sigs/krew/releases/latest/download/${KREW}.tar.gz" &&
  tar zxvf "${KREW}.tar.gz" &&
  ./"${KREW}" install krew
)
```

## usage

```sh
kubectl krew update

kubectl krew search

kubectl krew install oidc-login     # install plugin

kubectl access-matrix               # use plugin to see the level of access user has on namespaces
```

```sh
failed to retrieve plugin indexes: failed to list the remote URL for index default
unset GIT_CONFIG
```

## plugins

```sh
# access-matrix                   v0.5.0
# dds                             v0.1.0
# example                         v1.1.0
# krew                            v0.4.3
# oidc-login                      v1.25.1
# view-serviceaccount-kubeconfig  v2.2.8

kubectl example deployment

access-matrix

dds

view-serviceaccount-kubeconfig
```

## see also

- [[kubectl]]
- [krew.sigs.k8s.io/plugins/](https://krew.sigs.k8s.io/plugins/)
- [krew.sigs.k8s.io/docs/user-guide/setup/install/](https://krew.sigs.k8s.io/docs/user-guide/setup/install/)
