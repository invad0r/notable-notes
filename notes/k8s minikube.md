---
tags: [container, container/k8s]
title: k8s minikube
created: '2019-07-30T06:19:49.146Z'
modified: '2019-08-02T07:43:16.054Z'
---

# k8s minikube

`minikube` uses `libmachine` see also `docker machine`
> `k8s` = kuberntes (`k` + `numbers of letters to` + `s` )
> `i18n` = internationalization
> `l10n` = localization

### setup
```sh
brew install kubectl          # autocompleten should be configured 

brew cask install minikube

minikube completion bash > /usr/local/etc/bash_completion.d/minikube-completion

```


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

