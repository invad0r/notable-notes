---
title: kops
created: '2021-10-15T07:28:44.092Z'
modified: '2021-10-15T07:33:55.806Z'
---

# kops

> a way to get a production grade Kubernetes cluster up and running

## install

`brew install kops`

## usage

```sh
kops create cluster --zones=ZONE NAME

kops edit cluster NAME

kops update cluster NAME --yes

kops validate cluster --wait 10m

kops delete cluster --name
```

## see also

- [[kubectl]]
- [[gcloud]]
- [[minikube]]
- [kops.sigs.k8s.io](https://kops.sigs.k8s.io/)
