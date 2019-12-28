---
tags: [vmware]
title: govc find
created: '2019-08-26T08:32:59.799Z'
modified: '2019-12-28T15:55:05.978Z'
---

# govc find

## usage
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

govc find -type m -name "*packer*"                                                # find vms which contain packer

govc find . -type m -guest.ipAddress "10.32.22.8" -runtime.powerState poweredOn   # find host by IP

govc find -type n | gxargs -d '\n' -I% govc object.collect -s % name              # find all network and get object-names

govc find -i -type h -name vhost11.foo.bar          # get managed-object-reference: "HostSystem:host-29240"

govc find -type m -host $(govc find -i -type h -name vhost11.foo.bar)

# -host can be the HostSystem name or inventory path.   
govc find . -type h -datastore $(govc find -i ./datastore -name iso_images)         # find hosts that have the datastore mounted using

# find all vms running linux
govc find . -type m -runtime.powerState poweredOn -guest.guestFamily linuxGuest

govc find . -type m -runtime.powerState poweredOn -guest.guestId '*Linux*'

govc find . -type m -runtime.powerState poweredOn -guest.guestId '*[ubuntu][Linux]*'


govc vm.info -json ./vm/foo | jq '.VirtualMachines[].Guest.Net[] | .IpAddress[0]'   # find vm and its ip
```

## see also
- [[jq]]
- [find with -guest.ipAddress argument returns more than one result](https://github.com/vmware/govmomi/issues/1089)
