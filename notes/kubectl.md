---
tags: [container, container/k8s]
title: kubectl
created: '2019-07-30T06:19:49.145Z'
modified: '2020-12-30T09:03:44.785Z'
---

# kubectl
> kubectl controls the Kubernetes cluster manager

## installation
`brew install kubectl`

## usage
```sh
kubectl completion bash >$(brew --prefix)/etc/bash_completion.d/kubectl

KUBECONFIG

# merge config
KUBECONFIG=$HOME/.kube/config:file2:file3 kubectl config view --merge --flatten > \
  ~/.kube/merged_kubeconfig && mv ~/.kube/merged_kubeconfig ~/.kube/config


# flags
-v=6      # debug level 6

kubectl api-versions                              # get all supported api version

kubectl api-resources --sort-by=name -o wide      # get all objects

kubectl explain --api-version=apps/v1 replicaset
kubectl explain deployment.metadata
kubectl explain deployment.spec
kubectl explain deployment.spec.template.spec.containers --recursive    # 🤩 recursive: get a hierarchical view of the various fields.


kubectl config view
kubectl config view --flatten
kubectl config view --raw

kubectl config current-context
kubectl config get-contexts
kubectl config use-context CONTEXT


kubectl config get-clusters
kubectl config get-contexts


kubectl api-resources   # get all resource-names, alias and kinds
kubectl get
kubectl get all
kubectl get po POD_NAME -o yaml
kubectl get pod
kubectl get pods
kubectl get node
kubectl get nodes

kubectl run echoserver --image=gcr.io/google_containers/echoserver:1.4 --port=8080

kubectl cluster-info

kubectl explain po
kubectl explain --help


STDOUT | kubectl apply -f -
kubectl apply -f https://HOST/DEPLOYMENT.yaml

kubectl create -f kubia-manual.yaml

kubectl scale --replicas=1 kubia
kubectl scale replicationcontroller kubia --replicas=1


kubectl logs kubia-j582f
kubectl logs kubia-manual -c kubia

kubectl port-forward kubia-manual 8888:8080

kubectl run hello-minikube --image=k8s.gcr.io/echoserver:1.4 --port=8080

kubectl expose deployment hello-minikube --type=NodePort

kubectl delete deployment hello-minikube


# krew plugins
kubectl krew update

kubectl krew search

kubectl krew install oidc-login     # isntall plugin

kubectl access-matrix               # use plugin to see the level of access user has on namespaces
```

## see also
- [[kubectx]]
- [[kubens]]
- [[kubeseal]]
- [[kustomize]]
- [[kubernetes]]
- [[minikube]]
- [[gcloud]]
- [[yml]]
- [[jsonpath]]
