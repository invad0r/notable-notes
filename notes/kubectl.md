---
tags: [container]
title: kubectl
created: '2019-07-30T06:19:49.145Z'
modified: '2023-03-22T10:09:58.416Z'
---

# kubectl

> kubectl controls the Kubernetes cluster manager

## installation

```sh
brew install kubectl
kubectl completion bash >$(brew --prefix)/etc/bash_completion.d/kubectl`
```

## environment

```sh
KUBECONFIG          # alternative kube config
KUBE_EDITOR         # -
```

## flags

```sh
-v
--v=0 	# generally useful for this to always be visible to a cluster operator
--v=1 	# reasonable default log level if you don't want verbosity
--v=2 	# useful steady state information about the service and important log messages that may correlate to significant changes in the system. recommended default log level for most systems
--v=3 	# extended information about changes
--v=4 	# debug level verbosity
--v=5 	# trace level verbosity
--v=6 	# display requested resources
--v=7 	# display HTTP request headers
--v=8 	# display HTTP request contents
--v=9 	# display HTTP request contents without truncation of contents

-o=json 	                    # output a JSON formatted API object
-o=yaml 	                    # output a YAML formatted API object
-o=name 	                    # print only the resource name and nothing else
-o=wide 	                    # output in the plain-text format with any additional information, and for pods, the node name is included
-o=custom-columns=SPEC 	      # Print a table using a comma separated list of custom columns
-o=custom-columns-file=FILE   # print a table using the custom columns template in the FILE file
-o=jsonpath=TEMPLATE  	      # print the fields defined in a jsonpath expression
-o=jsonpath-file=FILE 	      # print the fields defined by the jsonpath expression in the FILE file

-A                        # all namespaces
-n, --namespace NS        # namespace scope for cli equest

--as=""         # Username to impersonate for the operation. User could be a regular user or a service account in a namespace.
--as-group=[]   # Group to impersonate for the operation, this flag can be repeated to specify multiple groups.
--as-uid=""     # UID to impersonate for the operation.

--certificate-authority=""    # path to a cert file for the certificate authority
--client-certificate=""       # path to a client certificate file for TLS
--client-key=""               # path to a client key file for TLS

--cluster CLUSTER     # name of the kubeconfig cluster to use
--context CONTEXT     # name of the kubeconfig context to use
--kubeconfig CONFIG   # path to the kubeconfig file to use for CLI requests.
-s, --server SERVER   # address and port of the Kubernetes API server
--token TOKEN         # bearer token for authentication to the API server
--user USER           # name of the kubeconfig user to use
--username USER       # Username for basic authentication to the API server
--password PASS       # password for basic authentication to the API server

--insecure-skip-tls-verify=false    # true: don't check server's certificate for validity, makes https connections insecure
--match-server-version=false        # Require server version to match client version

--profile="none"                   # name of profile to capture. One of (none|cpu|heap|goroutine|threadcreate|block|mutex)
--profile-output="profile.pprof"   # name of the file to write the profile to

--request-timeout="0"         # time to wait before giving up on a single request; time unit (1s, 2m, 3h); zero means don't timeout requests
--tls-server-name=""          # server name to use for server certificate validation. If it is not provided, the hostname used to contact the server is used
--warnings-as-errors=false    # treat warnings received from the server as errors and exit with a non-zero exit code
--version=false               # print version information and quit
```


### imperative commands / object configuration

```sh
kubectl diff      # object configuration
kubectl apply     # object configuration
``````

### declarative commands / object configuration

```sh
kubectl create      # object configuration
kubectl replace     # object configuration
kubectl delete      # object configuration
kubectl edit
kubectl scale
```

## usage

```sh
# merge config
KUBECONFIG="$HOME/.kube/config:file2:file3" kubectl config view --merge --flatten > ~/.kube/merged_kubeconfig \
  && mv ~/.kube/merged_kubeconfig ~/.kube/config

kubectl version -o yaml | yq e                                        # get client and server version
kubectl cluster-info                                                  # get addresses of the control plane and services
kubectl api-versions                                                  # get all supported api version

kubectl api-resources --sort-by=name -o wide                          # get all objects
kubectl api-resources | awk '{if ( $2 ~ /^[a-z]{2,7}$/) {print $0}}'  # get only aliased objects
kubectl api-resources --namespaced=true                               # all namespaced resources
kubectl api-resources --namespaced=false                              # all non-namespaced resources
kubectl api-resources -o name                                         # all resources with simple output (only the resource name)
kubectl api-resources -o wide                                         # all resources with expanded (aka "wide") output
kubectl api-resources --verbs=list,get                                # all resources that support the "list" and "get" request verbs
kubectl api-resources --verbs=list --namespaced -o name
kubectl api-resources --api-group=extensions                          # all resources in the "extensions" API group

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

kubectl get all     # get alle resoruce of current namespace
```

## node

```sh
kubectl get nodes

kubectl get node NODE_NAME -o name

kubectl get node NODE_NAME -o json | jq -r '.status.capacity.memory' | numfmt --from=iec-i --to=iec     # get avail memory


kubectl get nodes --selector='!node-role.kubernetes.io/master' --no-headers -o custom-columns=":metadata.name"

kubectl label node --all 'vpc.amazonaws.com/has-trunk-attached'-                # remove all labels 'vpc.ama..'


kubectl get node NODE_NAME -o yaml | yq -C e '.metadata.finalizers' -           # check for finalizers
kubectl patch NODE_NAME -p '{"metadata":{"finalizers":[]}}' --type=merge        # remove finalizers

kubectl drain NODE_NAME --force --ignore-daemonsets  --delete-local-data
kubectl cordon NODE_NAME
kubectl delete node NODE_NAME


kubectl get nodes -o go-template='{{printf "%-50s %-12s\n" "Node" "Taint"}}{{- range .items}}{{- if $taint := (index .spec "taints") }}{{- .metadata.name }}{{ "\t" }}{{- range $taint }}{{- .key }}={{ .value }}:{{ .effect }}{{ "\t" }}{{- end }}{{- "\n" }}{{- end}}{{- end}}'
```

## daemonset

```sh
kubectl rollout restart daemonset/DAEMONSET

kubectl -n kube-system patch daemonset aws-node \
  -p '{"spec": {"template": {"spec": {"nodeSelector": {"non-existing": "true"}}}}}'               # "scale down" daemonset
kubectl -n kube-system patch daemonset aws-node \
  --type json -p='[{"op": "remove", "path": "/spec/template/spec/nodeSelector/non-existing"}]'    # "scale up" daemonset
```

## pod

```sh
kubectl get po POD_NAME -o yaml
kubectl get pod
kubectl get pods --show-labels | awk '{print $6}' | column -s, -t
kubectl get pods -L 

kubectl exec -it POD -- curl -s http://10.1.0.3  # double dash `--` signals end of command options, if not set -s would be interpreted as kubectl flag
```

## service

> routes internal traffic

```sh
kubectl get svc SERVICE -o jsonpath="{.status.loadBalancer.ingress[*].hostname}"


kubectl apply   # makes incremental changes to an existing object
STDOUT | kubectl apply -f -
kubectl apply -f https://HOST/DEPLOYMENT.yaml

kubectl create  # creates a whole new object (previously non-existing / deleted) 
kubectl create -f kubia-manual.yaml

kubectl create whatever --dry-run=true -o yaml | kubectl apply -f -     # applying (declarative pattern) output of imperative command

kubectl delete deployment DEPLOYMENT


kubectl scale --replicas=1 kubia
kubectl scale replicationcontroller kubia --replicas=1

kubectl patch svc SERVICE -p '{"spec": {"type": "LoadBalancer"}}'


# edit a resource from the default editor
KUBE_EDITOR="nano" kubectl edit svc/SERVICE                  # use alternative editor
kubectl edit svc/SERVICE                                     # edit the service named 'docker-registry'
kubectl edit job.v1.batch/myjob -o json                      # edit the job 'myjob' in JSON using the v1 API format
kubectl edit deployment/mydeployment -o yaml --save-config   # edit the deployment 'mydeployment' in YAML and save the modified config in its annotation
```

## ingress

> manages external access to services, may provide load balancing, SSL termination and name-based virtual hosting

```sh
kubectl patch ingress INGRESS_NAME -p '{"metadata":{"finalizers":[]}}' --type=merge
```

## deployment

```sh
kubectl expose deployment DEPLOYMENT --type=NodePort

kubectl rollout restart deployment/nginx

kubectl rollout status deployment aws-load-balancer-controller

kubectl autoscale deployment DEPLOYMENT \
  --cpu-percent=50    `# target average CPU utilization` \
  --min=1             `# lower limit for the number of pods that can be set by the autoscaler` \
  --max=10            `# upper limit for the number of pods that can be set by the autoscaler`

kubectl patch deployment NAME --type=json -p='[{"op": "add", "path": "/spec/template/metadata/labels/this", "value": "that"}]'
```

## run

> running adhoc pod without yaml-manifest / create and run a particular image in a pod

```sh
kubectl run     # same as `kubectl create deployment`

kubectl run curl            --image=radial/busyboxplus:curl -i --tty   # then run: nslookup my-nginx

kubectl run echoserver      --image=gcr.io/google_containers/echoserver:1.4 --port=8080

kubectl run dnsutils        --image=tutum/dnsutils --generator=run-pod/v1 --command -- sleep infinity

kubectl run hello-minikube  --image=k8s.gcr.io/echoserver:1.4 --port=8080

kubectl run POD_NAME        --image=mongo:4.0 `# run pod on specific node `\
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
        }}}}}' \ 
  --command -- sleep infinity
```

## events

```sh
kubectl get events --sort-by='.lastTimestamp'

kubectl get events --sort-by=.metadata.creationTimestamp

kubectl get events --sort-by='.metadata.creationTimestamp' \
  -o 'go-template={{range .items}}{{.involvedObject.name}}{{"\t"}}{{.involvedObject.kind}}{{"\t"}}{{.message}}{{"\t"}}{{.reason}}{{"\t"}}{{.type}}{{"\t"}}{{.firstTimestamp}}{{"\n"}}{{end}}'
```

## logs

```sh
kubectl logs POD

kubectl logs POD -c CONTAINER

kubectl logs INGRESS_CONTROLLER -c controller \
  | jq -r '. | select(.nginx.status != "200") | .nginx | "\(.status): \(.remote_addr) \(.request) \(.proxy_upstream_name)"'
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
# failed to retrieve plugin indexes: failed to list the remote URL for index default
unset GIT_CONFIG

kubectl krew update

kubectl krew search

kubectl krew install oidc-login     # install plugin

kubectl access-matrix               # use plugin to see the level of access user has on namespaces
```

[krew.sigs.k8s.io/docs/user-guide/quickstart/](https://krew.sigs.k8s.io/docs/user-guide/quickstart/)

## see also

- [kubernetes.io/docs/reference/kubectl](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands)
- [[kubernetes]], [[oc]]
- [[helm]], [[kustomize]]
- [[cmctl]]
- [[nerdctl]]
- [[bazel]]
- [[kubectx]], [[kubens]]
- [[kubeseal]]
- [[kubeval]]
- [[kim]], [[opa]]
- [[aws]], [[eksctl]], [[kops]]
- [[minikube]], [[k3s]], [[k3d]], [[k0s]], [[k9s]]
- [[yml]], [[jsonpath]], [[go-template]]
- [[socat]]
- [stackoverflow.com/questions/47369351/kubectl-apply-vs-kubectl-create](https://stackoverflow.com/questions/47369351/kubectl-apply-vs-kubectl-create)
