---
tags: [vmware]
title: govc find
created: '2019-08-26T08:32:59.799Z'
modified: '2019-09-04T07:16:52.115Z'
---

# govc find

```sh
govc find --help

govc find -type p                                  
# -type 
#  a    VirtualApp
#  c    ClusterComputeResource
#  d    Datacenter
#  f    Folder
#  g    DistributedVirtualPortgroup
#  h    HostSystem
#  m    VirtualMachine
#  n    Network
#  o    OpaqueNetwork
#  p    ResourcePool
#  r    ComputeResource
#  s    Datastore
#  w    DistributedVirtualSwitch

govc find -type m -name "*packer*"  # find machines which contain packer
```

### find host by IP
```sh
govc find . -type m -guest.ipAddress "10.32.22.8" -runtime.powerState poweredOn
```

### find all network and get object-names
```sh
govc find -type n | gxargs -d '\n' -I% govc object.collect -s % name
```

### find vm and its ip
```sh
govc vm.info -json ./vm/foo | jq '.VirtualMachines[].Guest.Net[] | .IpAddress[0]'
```

### find hosts that have the datastore mounted using
```sh 
# -host can be the HostSystem name or inventory path.
govc find . -type h -datastore $(govc find -i ./datastore -name iso_images)
```

### find all vms running linux
```sh
govc find . -type m -runtime.powerState poweredOn -guest.guestFamily linuxGuest

govc find . -type m -runtime.powerState poweredOn -guest.guestId '*Linux*'

govc find . -type m -runtime.powerState poweredOn -guest.guestId '*[ubuntu][Linux]*'
```

## see also
- [[jq]]
- [govc find with -guest.ipAddress argument returns more than one result · GitHub](https://github.com/vmware/govmomi/issues/1089)
