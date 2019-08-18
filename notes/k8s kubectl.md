---
tags: [container, container/k8s]
title: k8s kubectl
created: '2019-07-30T06:19:49.145Z'
modified: '2019-08-02T07:43:19.373Z'
---

# k8s kubectl

```sh
kubectl get
kubectl get nodes
kubectl get node
kubectl get all
kubectl get po
kubectl get pods

kubectl get po kubia-4fm6l -o yaml
kubectl get pod kubia-manual -o yaml
kubectl get pod kubia-manual -o yaml > kubectl-get-pod_kubia-manual.yaml


kubectl cluster-info

kubectl config view
kubectl config use-context
kubectl config view
kubectl config get-contexts
kubectl config get-clusters
kubectl config get-contexts

kubectl explain po
kubectl explain --help

kubectl create -f kubia-manual.yaml
kubectl scale --help
kubectl scale --replicas=1 kubia
kubectl scale replicationcontroller kubia --replicas=1

kubectl logs kubia-j582f
kubectl logs kubia-manual
kubectl logs kubia-manual -c kubia
kubectl port-forward kubia-manual 8888:8080
kubectl logs kubia-manual -c kubia
```
