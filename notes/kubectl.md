---
tags: [container, container/k8s]
title: kubectl
created: '2019-07-30T06:19:49.145Z'
modified: '2019-12-26T11:32:51.136Z'
---

# kubectl
> kubectl controls the Kubernetes cluster manager

## installation
`brew install kubectl`

## usage
```sh
kubectl get

kubectl get nodes
kubectl get node

kubectl get all

kubectl get po
kubectl get pods

kubectl get po kubia-4fm6l -o yaml

kubectl get pod kubia-manual -o yaml > kubectl-get-pod_kubia-manual.yaml


kubectl cluster-info


kubectl config view

kubectl config use-context

kubectl config get-contexts
kubectl config get-clusters
kubectl config get-contexts


kubectl explain po

kubectl explain --help


kubectl create -f kubia-manual.yaml


kubectl scale --replicas=1 kubia

kubectl scale replicationcontroller kubia --replicas=1



kubectl logs kubia-j582f

kubectl logs kubia-manual -c kubia

kubectl port-forward kubia-manual 8888:8080

kubectl logs kubia-manual -c kubia
```

## see also
- [[kubernetes]]
- [[minikube]]
- [[gcloud]]
- [[yml]]
