---
tags: [container]
title: kustomize
created: '2020-10-12T10:34:55.454Z'
modified: '2022-01-25T13:09:34.459Z'
---

# kustomize

> customizing k8s resource configuration without templates and DSLs
> tool supporting template-free, structured customization of declarative configuration targeted to k8s-style objects.

## install

```sh
brew install kustomize

curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash
sudo mv kustomize /usr/local/bin/kustomize
```

## usage

```sh
kustomize install-completion                  # shell completion.

kustomize build PATH                          # print configuration per contents of kustomization.yaml

kustomize build . | kubectl apply -f -        # apply config zu k8s, same as `kubectl apply -k`




kustomize cfg                       # Commands for reading and writing configuration.

kustomize create                    # Create a new kustomization in the current directory

kustomize edit                      # Edits a kustomization file

kustomize fn                        # Commands for running functions against configuration.
```

## api reference

```sh
# kustomization.yaml
bases                   # deprecated
commonAnnotations
commonLabels
components
configMapGenerator
crds
generatorOptions
images
namePrefix
namespace
nameSuffix
patches                   # directive is newer, accepts more elements (annotation selector and label selector). 
                          # In addition, namespace and name can be regexes. 
                          # The target for patches can match more than one resource, all of which will be patched.
patchesJson6902           # older keyword which can only match one resource via target (no wildcards), and accepts only Gvk, namespace, and name.
patchesStrategicMerge
replicas
resources
secretGenerator
vars
```

## see also

- [[kubectl]]
- [[helm]]
- [[jsonnet]]
- [kubernetes-sigs.github.io/kustomize/](https://kubernetes-sigs.github.io/kustomize/)

