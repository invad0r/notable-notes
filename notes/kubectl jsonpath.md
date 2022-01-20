---
title: kubectl jsonpath
created: '2021-12-16T14:36:44.172Z'
modified: '2021-12-16T15:24:37.693Z'
---

# kubectl jsonpath


## usage

```sh
kubectl get nodes \
  -o jsonpath='{.items[*].status.addresses[?(@.type=="InternalDNS")].address}'

kubectl get pods \
  -o jsonpath='{range .items[*]}{@.metadata.name}{" "}{@.spec.containers[*].image}{"\n"}{end}'
```

## see also

- [[kubectl]]
- [[jq]]
- [[yq]]
