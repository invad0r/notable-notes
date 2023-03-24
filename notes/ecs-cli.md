---
tags: [container]
title: ecs-cli
created: '2022-09-30T07:14:13.775Z'
modified: '2023-03-22T10:19:58.638Z'
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
