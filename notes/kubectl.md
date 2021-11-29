---
tags: [container, container/k8s]
title: kubectl
created: '2019-07-30T06:19:49.145Z'
modified: '2021-11-13T09:45:40.378Z'
---

# kubectl

> kubectl controls the Kubernetes cluster manager


the `kubectl` tool supports three kinds of object management:

- imperative commands
- imperative object configuration -> `apply`, `diff`
- declarative object configuration -> `create`, `replace` and `delete`


## installation

- `brew install kubectl`
- `kubectl completion bash >$(brew --prefix)/etc/bash_completion.d/kubectl`

## usage

```sh
KUBECONFIG          # -
KUBE_EDITOR         # -
```

```sh
-v=6                      # debug level 6
-o                        # output format [json|yaml|wide]

--kubeconfig CONFIG
--namespace NAMESPACE
--context CONTEXT
```

```sh
# merge config
KUBECONFIG="$HOME/.kube/config:file2:file3" kubectl config view --merge --flatten > ~/.kube/merged_kubeconfig && mv ~/.kube/merged_kubeconfig ~/.kube/config

kubectl version -o yaml | yq e                                        # get client and server version
kubectl cluster-info                                                  # get addresses of the control plane and services
kubectl api-versions                                                  # get all supported api version
kubectl api-resources --sort-by=name -o wide                          # get all objects
kubectl api-resources | awk '{if ( $2 ~ /^[a-z]{2,7}$/) {print $0}}'  # get only aliased objects

kubectl explain po
kubectl explain --help
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

kubectl get nodes
kubectl get nodes -o jsonpath='{.items[*].status.addresses[?(@.type=="InternalDNS")].address}'

kubectl get nodes \
  --selector='!node-role.kubernetes.io/master' \
  --no-headers \
  -o custom-columns=":metadata.name"

kubectl get node NODE -ojson | jq -r '.status.capacity.memory' | numfmt --from=iec-i --to=iec     # get avail memory

kubectl get po POD_NAME -o yaml
kubectl get pod
kubectl get pods --show-labels | awk '{print $6}' | column -s, -t
kubectl get pods -L 


kubectl apply   # makes incremental changes to an existing object
STDOUT | kubectl apply -f -
kubectl apply -f https://HOST/DEPLOYMENT.yaml

kubectl create  # creates a whole new object (previously non-existing / deleted) 
kubectl create -f kubia-manual.yaml

kubectl create whatever --dry-run=true -o yaml | kubectl apply -f -     # applying (declarative pattern) output of imperative command

kubectl delete deployment DEPLOYMENT


kubectl scale --replicas=1 kubia
kubectl scale replicationcontroller kubia --replicas=1


# edit a resource from the default editor
KUBE_EDITOR="nano" kubectl edit svc/SERVICE                  # use alternative editor
kubectl edit svc/SERVICE                                     # edit the service named 'docker-registry'
kubectl edit job.v1.batch/myjob -o json                      # edit the job 'myjob' in JSON using the v1 API format
kubectl edit deployment/mydeployment -o yaml --save-config   # edit the deployment 'mydeployment' in YAML and save the modified config in its annotation

kubectl expose deployment DEPLOYMENT --type=NodePort

kubectl exec -it POD -- curl -s http://10.1.0.3  # double dash `--` signals end of command options, if not set -s would be interpreted as kubectl flag
```

## run

> running adhoc pod without yaml-manifest

```sh

kubectl run     # same as `kubectl create deployment`

kubectl run echoserver --image=gcr.io/google_containers/echoserver:1.4 --port=8080

kubectl run dnsutils --image=tutum/dnsutils --generator=run-pod/v1 --command -- sleep infinity

kubectl run hello-minikube --image=k8s.gcr.io/echoserver:1.4 --port=8080

kubectl run POD_NAME \
  --image=mongo:4.0  \
  --overrides='{"apiVersion": "v1", "spec": {
    "affinity": {
      "nodeAffinity": {
        "requiredDuringSchedulingIgnoredDuringExecution": {
          "nodeSelectorTerms": [{
              "matchFields": [{
                  "key": "metadata.name",
                  "operator": "In",
                  "values": ["NODE_NAME"]
                }]
            }]
        }}}}}' \                                  `# run pod on specific node `
  --command -- sleep infinity
```

## logs

```sh
kubectl logs POD

kubectl logs POD -c CONTAINER

kubectl logs INGRESS_CONTROLLER -c controller | jq -r '. | select(.nginx.status != "200") | .nginx | "\(.status): \(.remote_addr) \(.request) \(.proxy_upstream_name)"'
```

## port-forward 

> forward one or more local ports to a pod (requires node to have `socat` installed)

```sh
kubectl port-forward pod/mypod 5000 6000                                    # listen on ports 5000 and 6000 locally, forwarding data to/from ports 5000 and 6000 in the pod
kubectl port-forward deployment/mydeployment 5000 6000                      # listen on ports 5000 and 6000 locally, forwarding data to/from ports 5000 and 6000 in a pod selected by the deployment
kubectl port-forward service/myservice 8443:https                           # listen on port 8443 locally, forwarding to the targetPort of the service's port named "https" in a pod selected by the service

kubectl port-forward pod/mypod 8888:5000                                    # listen on port 8888 locally, forwarding to 5000 in the pod
kubectl port-forward kubia-manual 8888:8080
kubectl port-forward pod/mypod :5000                                        # listen on a random port locally, forwarding to 5000 in the pod

kubectl port-forward --address 0.0.0.0 pod/mypod 8888:5000                  # listen on port 8888 on all addresses, forwarding to 5000 in the pod
kubectl port-forward --address localhost,10.19.21.23 pod/mypod 8888:5000    # listen on port 8888 on localhost and selected IP, forwarding to 5000 in the pod
```



## secrets

```sh
kubectl get secrets --field-selector type=kubernetes.io/tls     # list only certificate secrets

kubectl get secrets SECRET -o json | jq -r '.data | to_entries[] | "\(.key): \(.value | @base64d)"';    # print secrets base64-decoded
```

## krew plugins

```sh
kubectl krew update

kubectl krew search

kubectl krew install oidc-login     # install plugin

kubectl access-matrix               # use plugin to see the level of access user has on namespaces
```

## see also

- [[oc]]
- [[helm]]
- [[kustomize]]
- [[bazel]]
- [[kubectx]]
- [[kubens]]
- [[kubeseal]]
- [[kubeval]]
- [[kubernetes]]
- [[kim]]
- [[kops]]
- [[minikube]]
- [[opa]]
- [[yml]]
- [[jsonpath]]
- [[socat]]
- [stackoverflow.com/questions/47369351/kubectl-apply-vs-kubectl-create](https://stackoverflow.com/questions/47369351/kubectl-apply-vs-kubectl-create)
