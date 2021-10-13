---
title: eksctl
created: '2021-10-13T09:32:12.878Z'
modified: '2021-10-13T09:36:43.449Z'
---

# eksctl

> for creating and managing clusters on [[aws]] EKS, written in [[go]], uses `cloudformation`, was created by weaveworks

## install
`brew tap weaveworks/tap && brew install weaveworks/tap/eksctl`


## usage

```sh
eksctl get cluster --name=NAME --region=REGION

eksctl create cluster --name=CLUSTER-1 --nodes=4
```

## see also

- [eksctl.io](https://eksctl.io/)
- [[kubectl]]
- [[gcloud]]
