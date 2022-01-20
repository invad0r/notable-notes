---
title: eksctl
created: '2021-10-13T09:32:12.878Z'
modified: '2022-01-17T15:43:18.535Z'
---

# eksctl

> for creating and managing clusters on [[aws]] EKS, written in [[go]], uses `cloudformation`, was created by weaveworks

## install

`brew tap weaveworks/tap && brew install weaveworks/tap/eksctl`

## usage

```sh
eksctl get cluster --name=NAME --region=REGION

eksctl create cluster --name=CLUSTER --nodes=4

# create the identity mapping within the cluster
eksctl create iamidentitymapping \
  --cluster CLUSTER --arn ROLE_ARN \
  --group system:masters --username admin


# completely scaling down nodes to zero use this (max=0 threw errors)
eksctl scale nodegroup \
  --cluster CLUSTERNAME \
  --name NODEGROUPNAME \
  --nodes 0 \
  --nodes-max 1 \
  --nodes-min 0


aws eks get-token --cluster-name CLUSTERNAME | jq -r '.status.token'


eksctl utils associate-iam-oidc-provider --cluster CLUSTER --approve
```

## see also

- [[aws]]
- [[kubectl]]
- [[helm]]
- [[nerdctl]]
- [[gcloud]]
- [eksctl.io](https://eksctl.io/)
