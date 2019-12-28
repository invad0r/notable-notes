---
tags: [brew, container, container/k8s]
title: minikube
created: '2019-07-30T06:19:49.146Z'
modified: '2019-12-26T11:32:11.201Z'
---

# minikube

> `minikube` uses `libmachine` see also `docker machine`

## installation
```sh
brew cask install minikube

minikube completion bash > /usr/local/etc/bash_completion.d/minikube-completion
```

## usage
```sh
minikube start

kubectl run hello-minikube --image=k8s.gcr.io/echoserver:1.4 --port=8080

kubectl expose deployment hello-minikube --type=NodePort


kubectl get pod

curl $(minikube service hello-minikube --url)

minikube ssh


kubectl delete deployment hello-minikube

minikube stop
```

## see also
- [[kubectl]]
- [[kubernetes]]
