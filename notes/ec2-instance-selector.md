---
title: ec2-instance-selector
created: '2022-01-18T19:33:51.186Z'
modified: '2022-01-18T19:48:06.396Z'
---

# ec2-instance-selector

> recommends instance types based on resource criteria like vcpus and memory

## install

`brew tap aws/tap && brew install ec2-instance-selector`

## usage

```sh
AWS_PROFILE=PROFILE ec2-instance-selector --service eks

ec2-instance-selector --memory 4 --vcpus 2 --cpu-architecture x86_64 -r REGION -o table

ec2-instance-selector --network-performance 100 --usage-class spot -r REGION
```

## see also

- [[aws]]
