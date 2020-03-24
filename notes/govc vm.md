---
deleted: true
tags: [vmware]
title: govc vm
created: '2019-09-03T06:58:09.766Z'
modified: '2020-03-18T16:04:02.212Z'
---

# govc vm

## vm
```sh
govc vm.info -json ${vm} | jq '.VirtualMachines[].Guest.Net[] | .IpConfig | .IpAddress'

govc vm.info -json ${vm} | jq '.VirtualMachines[]' | grep -o -E '10\.32\.[0-9]{1,3}\.[0-9]{1,3}';

govc vm.info -json $REPLY | jq '.VirtualMachines[].Config.Hardware.Device[] | select(.Key== 2000) | .CapacityInBytes';
```

## see also
- [[govc]]
- [[jq]]
