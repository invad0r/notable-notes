---
tags: [linux, vmware]
title: photonOS
created: '2019-07-30T06:19:49.205Z'
modified: '2019-07-30T08:49:54.088Z'
---

# photonOS


```
 +----------------------------------------------------------------+
 |                        photon                                  |
 +----------------------------------------------------------------+
 |             vic (vsphere integrated container)                 |
 +----------------------------------------------------------------+
 | engine                | registry       | management-portal     |
 | vSphere Administrator | VMware Harbrog | VMware Admira         |
 |                       |                | (ui for pro^isioners) |
 +----------------------------------------------------------------+
```

container host optimized for vsphere & cloud computing using `systemd` and `tinyDNF`

`RPM-OSTree`
-> bootable immutable versioned FS-Trees
-> client/server architecture

[Downloading Photon OS · vmware/photon Wiki · GitHub](https://github.com/vmware/photon/wiki/Downloading-Photon-OS)

## kickstart
```sh
mkisofs -R -l -L -D -b isolinux/isolinux.bin \
  -c isolinux/boot.cat \
  -no-emul-boot \
  -boot-load-size 4 \
  -boot-info-table \
  -V \
  "PHOTON_$(date +%Y%m%d)" . > /home/ubuntu/PHOTON_$(date +%Y%m%d).iso
```


## install photon

[Getting started with Photon OS and vSphere Integrated Containers - CormacHogan.com](https://cormachogan.com/2016/04/07/getting-started-photon-os-vsphere-integrated-containers/)
[Install vSphere Integrated Containers v0.1 via VMware Photon OS TP2 – think-v](http://blog.think-v.com/?p=3649)
## ssh
```sh
# Enable root login in /etc/ssh/sshd_config
sed -i 's/#PasswordAuthentication/PasswordAuthentication/g' /etc/ssh/sshd_config
sed -i 's/PermitRootLogin no/PermitRootLogin yes/g' /etc/ssh/sshd_config
systemctl restart sshd
```

## installed packages

https://github.com/vmware/photon/blob/master/common/data/packages_minimal.json
https://github.com/vmware/photon/blob/master/common/data/packages_full.json

## dockerd
```sh
systemctl stop docker

vim /etc/default/docker

  DOCKER_OPTS="-H tcp://0.0.0.0:2375 -H unix:///var/run/docker.sock"
  
vim /lib/systemd/system/docker.service
  ..
  ExecStart=/usr/bin/dockerd -H tcp://0.0.0.0:2375 -H unix://
  
iptables -A INPUT -p tcp --dport 2375 -j ACCEPT   # ! not safe for restart

systemctl start docker
```
[How to enable Docker Remote API on Photon OS - Cloud Native Apps](https://blogs.vmware.com/cloudnative/2016/09/28/enable-docker-remote-api-photon-os/)
