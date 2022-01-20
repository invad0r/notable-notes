---
tags: [container]
title: argocd
created: '2020-10-26T12:29:59.372Z'
modified: '2022-01-17T13:55:14.545Z'
---

# argocd

> declarative, gitops continuous delivery tool for k8s

## install

```sh
brew install argocd                   # install cli

kubectl create namespace argocd       # install argocd on cluster
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/core-install.yaml
```

## usage

```sh
argocd login HOST

argocd app create guestbook \
  --repo https://github.com/argoproj/argocd-example-apps.git \
  --path guestbook \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace default
```

## see also

- [[flux]]
- [[gitops]]
- [[kubectl]]
- [[minikube]]
