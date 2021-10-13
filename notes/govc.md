---
tags: [vmware]
title: govc
created: '2019-07-30T06:19:49.075Z'
modified: '2021-10-06T12:16:29.018Z'
---

# govc

> govc is an vSphere CLI built on govmomi, the vSphere Go SDK. It has a robust inventory browser command.

## usage

```sh
# ls
govc ls -h

govc ls -l '*'

govc ls -l '/na Hamburg/host/'

govc ls datastore

# managed object IDs
govc ls -l -i "/na Hamburg/network"
 # Network:network-42744 /na Hamburg/network/Docker-Netz DMZ ..

# reverse search, supply the -L switch
govc ls -i -l -L "Network:network-42742"
 # Network:network-42742 /na Hamburg/network/Docker-Netz Test 

# list ResourcePool 
govc ls -l 'host/*' | grep ResourcePool | awk '{print $1}' # | xargs -n1 -t govc pool.info

govc pool.info "/na Hamburg/host/naCluster02/Resources"


# host
govc host.info -host='/na Hamburg/host/naCluster02/vhost01.domain.net'

govc host.service.ls -host='/na Hamburg/host/naCluster02/vhost06.domain.net'

host.service.ls

govc host.info -host='/na Hamburg/host/naCluster02/vhost01.domain.net'

govc host.service.ls -host='/na Hamburg/host/naCluster02/vhost06.domain.net'

govc host.storage.info -host='/na Hamburg/host/naCluster02/vhost06.domain.net'
 
govc host.info -host='/na Hamburg/host/naCluster02/vhost01.domain.net'
# Name:              vhost01.domain.net
#   Path:            /na Hamburg/host/naCluster02/vhost01.domain.net


govc datacenter.info                              
govc host.info -host='/na Hamburg/host/naCluster02/vhost01.domain.net'                           
govc host.service.ls -host='/na Hamburg/host/naCluster02/vhost06.domain.net'                              



# datastore
govc datastore.ls -ds=datastore2 -l

govc find vm -type m -datastore $(govc find -i datastore -name datastore3)

for i in $(govc find vm -type m | grep -i "node" | cut -d/ -f2); do
  DATASTORE="$( govc vm.info -json "$i" \
      | jq --raw-output '.VirtualMachines[].Config.Hardware.Device[] | select(.DeviceInfo.Label=="CD/DVD drive 1" ) | .Backing.FileName')";
  printf "%s: %s" "$i" "$DATASTORE";
done


# vm - virtualmachine
govc vm.info -json ${vm} | jq '.VirtualMachines[].Guest.Net[] | .IpConfig | .IpAddress'

govc vm.info -json ${vm} | jq '.VirtualMachines[]' | grep -o -E '10\.32\.[0-9]{1,3}\.[0-9]{1,3}';

govc vm.info -json $REPLY | jq '.VirtualMachines[].Config.Hardware.Device[] | select(.Key== 2000) | .CapacityInBytes';

# restart vm
for vm in $(govc find -type m -name "swarm-*.ddev.domain.net"); do
  UUID=$(govc vm.info -json "$vm" | jq -r '.VirtualMachines[].Summary.Config.Uuid');
  echo "$vm"
  echo govc vm.power -off=true -vm.uuid=$UUID \&\& govc vm.power -on=true -vm.uuid=$UUID;
done

# tags
govc tags.ls

govc tags.attached.ls -r vm/stats-db.node.dint.domain.net

govc tags.attached.ls backup_daily2230_noQuiese

govc object.collect -json VirtualMachine:vm-365


# tasks
govc tasks -n=20 -f     # show current vsphere tasks


# metrics
govc metric.ls ./vm/mq-1.node.dint.domain.net
govc metric.sample ./vm/mq-1.node.dint.domain.net cpu.usage.average


# snapshot
govc snapshot.tree -vm ./vm/mq-1.node.dint.domain.net -D -i -d

govc snapshot.create -vm ./vm/gitlab.node.dint.domain.net pre-gitlab-v12-upgrade
```

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

- [find with -guest.ipAddress argument returns more than one result](https://github.com/vmware/govmomi/issues/1089)

## see also

- [[jq]]
- [velenux.wordpress.com/automate-your-vcenter-interactions-from-the-linux-commandline-with-govmomi-and-govc](https://velenux.wordpress.com/2016/09/19/automate-your-vcenter-interactions-from-the-linux-commandline-with-govmomi-and-govc/)
- [Network info · Issue #742 · vmware/govmomi · GitHub](https://github.com/vmware/govmomi/issues/742)
- [datastore.upload broken pipe · Issue #832 · vmware/govmomi · GitHub](https://github.com/vmware/govmomi/issues/832)
- [pool.info command appears broken · Issue #203 · vmware/govmomi · GitHub](https://github.com/vmware/govmomi/issues/203#issuecomment-70699130)
