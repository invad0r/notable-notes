---
tags: [container, container/k8s]
title: kubectl
created: '2019-07-30T06:19:49.145Z'
modified: '2021-03-22T16:04:30.811Z'
---

# kubectl
> kubectl controls the Kubernetes cluster manager

## installation
- `brew install kubectl`
- `kubectl completion bash >$(brew --prefix)/etc/bash_completion.d/kubectl`

## usage
```sh
# environment variables
#   KUBECONFIG
#   KUBE_EDITOR

# flags
#   -v=6      debug level 6
#   -o        output format [json|yaml|wide] 


# merge config
KUBECONFIG=$HOME/.kube/config:file2:file3 kubectl config view --merge --flatten > ~/.kube/merged_kubeconfig && mv ~/.kube/merged_kubeconfig ~/.kube/config


kubectl api-versions                              # get all supported api version

kubectl api-resources --sort-by=name -o wide      # get all objects

kubectl explain --api-version=apps/v1 replicaset
kubectl explain deployment.metadata
kubectl explain deployment.spec
kubectl explain deployment.spec.template.spec.containers --recursive    # 🤩 recursive: get a hierarchical view of the various fields.


kubectl config view [--flatten|--raw]
kubectl config current-context
kubectl config get-contexts
kubectl config use-context CONTEXT
kubectl config get-clusters
kubectl config set-context CONTEXT --user minikube --cluster minikube --namespace NAMESPACE
kubectl config use-context CONTEXT


kubectl api-resources   # get all resource-names, alias and kinds
kubectl get
kubectl get all

kubectl get node
kubectl get nodes -o jsonpath='{.items[*].status.addresses[?(@.type=="InternalDNS")].address}'

kubectl get po POD_NAME -o yaml
kubectl get pod
kubectl get pods --show-labels | awk '{print $6}' | column -s, -t
kubectl get pods -L 


kubectl run echoserver --image=gcr.io/google_containers/echoserver:1.4 --port=8080

kubectl cluster-info

kubectl explain po
kubectl explain --help

# running adhoc pod without yaml-manifest
kubectl run dnsutils --image=tutum/dnsutils --generator=run-pod/v1 --command -- sleep infinity

STDOUT | kubectl apply -f -
kubectl apply -f https://HOST/DEPLOYMENT.yaml

kubectl create -f kubia-manual.yaml

kubectl scale --replicas=1 kubia
kubectl scale replicationcontroller kubia --replicas=1


# edit a resource from the default editor
KUBE_EDITOR="nano" kubectl edit svc/SERVICE                  # use alternative editor
kubectl edit svc/SERVICE                                     # edit the service named 'docker-registry'
kubectl edit job.v1.batch/myjob -o json                      # edit the job 'myjob' in JSON using the v1 API format
kubectl edit deployment/mydeployment -o yaml --save-config   # edit the deployment 'mydeployment' in YAML and save the modified config in its annotation


kubectl logs kubia-j582f
kubectl logs kubia-manual -c kubia


kubectl run hello-minikube --image=k8s.gcr.io/echoserver:1.4 --port=8080


kubectl expose deployment DEPLOYMENT --type=NodePort

kubectl delete deployment DEPLOYMENT


# port-forward - forward one or more local ports to a pod (requires node to have `socat` installed)
kubectl port-forward pod/mypod 5000 6000                                    # listen on ports 5000 and 6000 locally, forwarding data to/from ports 5000 and 6000 in the pod
kubectl port-forward deployment/mydeployment 5000 6000                      # listen on ports 5000 and 6000 locally, forwarding data to/from ports 5000 and 6000 in a pod selected by the deployment
kubectl port-forward service/myservice 8443:https                           # listen on port 8443 locally, forwarding to the targetPort of the service's port named "https" in a pod selected by the service

kubectl port-forward pod/mypod 8888:5000                                    # listen on port 8888 locally, forwarding to 5000 in the pod
kubectl port-forward kubia-manual 8888:8080
kubectl port-forward pod/mypod :5000                                        # listen on a random port locally, forwarding to 5000 in the pod

kubectl port-forward --address 0.0.0.0 pod/mypod 8888:5000                  # listen on port 8888 on all addresses, forwarding to 5000 in the pod
kubectl port-forward --address localhost,10.19.21.23 pod/mypod 8888:5000    # listen on port 8888 on localhost and selected IP, forwarding to 5000 in the pod


kubectl exec -it POD -- curl -s http://10.1.0.3  # double dash `--` signals end of command options, if not set -s would be interpreted as kubectl flag
```
## krew plugins
```sh
kubectl krew update

kubectl krew search

kubectl krew install oidc-login     # install plugin

kubectl access-matrix               # use plugin to see the level of access user has on namespaces
```

## see also
- [[kubectx]]
- [[kubens]]
- [[kubeseal]]
- [[kubeval]]
- [[helm]]
- [[kustomize]]
- [[kubernetes]]
- [[minikube]]
- [[opa]]
- [[yml]]
- [[jsonpath]]
- [[socat]]
