---
tags: [container]
title: oc
created: '2021-10-20T09:24:01.749Z'
modified: '2023-03-22T11:00:40.371Z'
---

# oc

> cli for openshift a k8s distribution

## install

```sh
brew install openshift-cli

oc completion bash > $(brew --prefix)/etc/bash_completion.d/oc
```


## usage

```sh
oc config set-credentials USER

oc config set-cluster CLUSTER

oc config set-credentials vipin --token=TOKEN


oc get useroauthaccesstokens
oc describe useroauthaccesstokens TOKEN

oc project          # view current project

oc status           # info about current project

oc api-resources    # list supported api resources
```

## see also

- [[crc]]
- [[kubectl]]
- [redhat.com/en/blog/openshift-and-kubernetes-whats-difference](https://www.redhat.com/en/blog/openshift-and-kubernetes-whats-difference)
