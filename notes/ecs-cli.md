---
title: ecs-cli
created: '2022-09-30T07:14:13.775Z'
modified: '2022-11-23T08:35:21.222Z'
---

# ecs-cli

## install

```sh
brew install amazon-ecs-cli
```

## usage

```sh
aws ecs list-clusters --region eu-central-1 | jq -r '.clusterArns[]'

ecs-cli ps --cluster CLUSTER_ARN

ecs-cli ps --cluster CLUSTER_ARN --desired-status RUNNING 
```

## see also

- [[aws]]
- [[session-manager-plugin]]
