---
tags: [container]
title: max-pods-calculator
created: '2022-03-29T14:57:24.315Z'
modified: '2023-03-24T08:21:00.855Z'
---

# max-pods-calculator

> script to calculate maxPods value to be used when starting up the kubelet

## install

```sh
curl -LO https://raw.githubusercontent.com/awslabs/amazon-eks-ami/master/files/max-pods-calculator.sh
chmod +x max-pods-calculator.sh
```

## option

```sh
-h, --help                          # print this help
    --instance-type                 # Specify the instance type to calculate max pods value
    --instance-type-from-imds       # flag if the instance type should be fetched from IMDS
    --cni-version                   # specify the version of the CNI (example - 1.7.5)
    --cni-custom-networking-enabled # indicate if CNI custom networking mode has been enabled
    --cni-prefix-delegation-enabled # indicate if CNI prefix delegation has been enabled
    --cni-max-eni                   # specify how many ENIs should be used for prefix delegation. Defaults to using all ENIs per instance
    --show-max-allowed              # show max number of Pods allowed to run in Worker Node. Otherwise the script will show the recommended value
```

## usage

```sh
AWS_PROFILE=PROFILE ./max-pods-calculator.sh --instance-type m5.large --cni-version 1.9.0-eksbuild.1

./max-pods-calculator.sh --instance-type m5.large --cni-version 1.10.1-eksbuild.1
```

## see also

- [[aws]]
- [docs.aws.amazon.com/eks/latest/userguide/choosing-instance-type](https://docs.aws.amazon.com/eks/latest/userguide/choosing-instance-type.html)
