---
tags: [virtualization]
title: vm disk image
created: '2019-07-30T06:19:49.264Z'
modified: '2019-08-18T14:05:34.203Z'
---

# vm disk image

## file formats for virtual machines
```
OVF   - Open Virtualization Format XML based, 
        describes single vm or virtual appliance,
        contains information about format of virtual-disk and
        description of virtual hardware that should be emulated 

OVA   - Open Virtualization Applicance OVF + supporing file (disk-images, ..) 
```
## formats for disk images 
```
.vid   - VirtualBox
.vmdk  - VMWare (many different versions!)
.vhd   - Microsoft (Virtual PC)
raw    - (.IMG,.ISO,..) 
````
[OVF? OVA? VMDK? – File Formats and Tools for Virtualization](https://spin.atomicobject.com/2013/06/03/ovf-virtual-machine/)

## extract VMDK

rename `.ova` to `.tar` and extract `.vmdk`

[How to convert an OVA virtual machine to VHD](https://www.rootusers.com/how-to-convert-an-ova-virtual-machine-to-vhd/)
[How to convert RAW image to VDI and otherwise](https://blog.sleeplessbeastie.eu/2012/04/29/virtualbox-convert-raw-image-to-vdi-and-otherwise/)
