---
tags: [virtualization, vmware]
title: vsphere
created: '2019-07-30T06:19:49.264Z'
modified: '2022-02-02T10:03:19.271Z'
---

# vsphere

> vmware vSphere is a cloud computing virtualization platform

> `VID`  `vSphere Installation Bundle`
> `VUM`  `vSphere Update Manager`
> `VDVS` `vSphere`
> `VMCI` `Virtual Machine Communication Interface`

## vm bootorder via .vmx

```sh
bios.forceSetupOnce = "TRUE"
bios.bootOrder = "hdd"
```

## mob - managed object browser

`https://vcenter1.domain.net/mob/`

```
RetrieveProductComponents -> Invoke Method 
  -> rootFolder/group-d1
  -> childEntity/datacenter-21
  -> datastore/datastore-29
  -> 
```

photon-template: 
- `https://vcenter1.domain.net/mob/?moid=vm%2d97645`
- `https://vcenter1.domain.net/mob/?moid=vm%2d97645&doPath=summary%2econfig` # UUID

## see also

- [Can't Change BIOS Settings on VM in Fusion 5](https://www.eager0.com/2013/02/cant-change-bios-settings-on-vm-in.html)
- [Looking up Managed Object Reference](https://kb.vmware.com/s/article/1017126)
- [vSphere Integrated Containers by VMware®](https://vmware.github.io/vic-product/)
- [GitHub - vmware/vic: Integrated containers engine on vSphere](https://github.com/vmware/vic#project-status)
- [harbor/user_guide.md at master · vmware/harbor · GitHub](https://github.com/vmware/harbor/blob/master/docs/user_guide.md)
- [Install vSphere Integrated Containers v0.1 via VMware Photon OS TP2 – think-v](http://blog.think-v.com/?p=3649)
