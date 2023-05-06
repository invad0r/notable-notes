---
tags: [container]
title: helm
created: '2021-06-04T08:40:48.010Z'
modified: '2023-05-02T07:09:43.180Z'
---

# helm

> package manager for `k8s`

## install

```sh
brew install helm

curl -sSL https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash
```

## environment vairables

```sh
HELM_CACHE_HOME                     # alt location for storing cached files
HELM_CONFIG_HOME                    # alt location for storing Helm configuration
HELM_DATA_HOME                      # alt location for storing Helm data
HELM_DEBUG                          # indicate whether or not Helm is running in Debug mode
HELM_DRIVER                         # backend storage driver: configmap, secret, memory, postgres                                                  
HELM_DRIVER_SQL_CONNECTION_STRING   # connection string the SQL storage driver should use
HELM_MAX_HISTORY                    # maximum number of helm release history
HELM_NAMESPACE                      # namespace used for the helm operations
HELM_NO_PLUGINS                     # ble plugins. Set HELM_NO_PLUGINS=1 to disable plugins
HELM_PLUGINS                        # path to plugins dir
HELM_REGISTRY_CONFIG                # path to registry config file
HELM_REPOSITORY_CACHE               # path to repository cache dir
HELM_REPOSITORY_CONFIG              # path to repositories file
KUBECONFIG                          # alt k8s config - default `.kube/config`
HELM_KUBEAPISERVER                  # k8s API Server Endpoint for auth
HELM_KUBECAFILE                     # k8s certificate authority file
HELM_KUBEASGROUPS                   # set groups to use for impersonation using a comma-separated list
HELM_KUBEASUSER                     # Username to impersonate for the operation
HELM_KUBECONTEXT                    # name of the kubeconfig context
HELM_KUBETOKEN                      # bearer kube-token used for auth
```

## usage

```sh
helm help       # learn more about the available Helm commands
helm get -h     # or type a command followed by -h flag

helm list                      # lists all of the releases for a specified namespace
helm ls

helm status   RELEASE_NAME
helm history  RELEASE_NAME
helm rollback RELEASE_NAME [REVISION]

helm env

helm search                   # search for charts
helm search repo [REPONAME]

helm pull                       # download chart to local dir
helm pull stable/CHART --untar  # optionally untar chart

helm install                                              # upload chart to k8s
helm install bitnami/mysql --generate-name
helm install --debug --dry-run CHART ./PATH               # test the template rendering, but not actually install anything

helm repo add stable  https://charts.helm.sh/stable       # add as "stable" -> prepends "stable/REPO"
helm repo add datadog https://helm.datadoghq.com
helm repo add bitnami https://charts.bitnami.com/bitnami

helm repo update

helm show all CHART
helm show chart datadog --repo https://helm.datadoghq.com --version 2.6.11
helm show chart bitnami/mysql
helm show all bitnami/mysql


helm uninstall mysql-1612624192   # uninstall release


helm template CHART                                   # render chart templates locally and display the output
helm template CHART -x templates/deployment.yaml      # render just one template in a chart
```

## plugin

```sh
helm plugin install https://github.com/databus23/helm-diff

helm diff revision RELEASE 100 55
```

## helmfile

```yaml
        {{/* if dig "monitoring" "enabled" false .Values.mrz */}}
        {{if (((.Values.mrz).monitoring).enabled) }}
```

## see also

- [[kubectl]]
- [[kustomize]]
- [helm.sh/docs/intro/quickstart](https://helm.sh/docs/intro/quickstart/)
