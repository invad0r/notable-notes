---
tags: [container]
title: kubeconform
created: '2023-04-20T07:33:37.232Z'
modified: '2023-05-05T06:56:55.719Z'
---

# kubeconform

> manifest validation tool for CI or local validation of k8s configuration

## install

```sh
brew install kubeconform
```

## usage

```sh
helm template . | kubeconform

kubeconform \
  -kubernetes-version 3.8.0  \
  -schema-location 'https://raw.githubusercontent.com/garethr/openshift-json-schema/master/{{ .NormalizedKubernetesVersion }}-standalone{{ .StrictSuffix }}/{{ .ResourceKind }}.json'  \
  -summary fixtures/valid.yaml
```

## see also

- [[helm]]
- [[kubectl]]
