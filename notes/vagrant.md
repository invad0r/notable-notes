---
tags: [iac]
title: vagrant
created: '2019-07-30T06:19:49.078Z'
modified: '2020-05-14T08:40:48.802Z'
---

# vagrant

> cli utility for managing the lifecycle of virtual machines

## usage
```sh
vagrant init --minimal centos/7                   # create minimal Vagrantfile

vagrant init --output Vagrantfile.long centos/7   # different Vagrantfile


vagrant up                                        # start vm from Vagrantfile

vagrant status

vagrant ssh                                       # ssh into vm

vagrant destroy --force                           # destroy without confirmation


vagrant box list

vagrant box add chef/centos-6.5

vagrant ssh-config                    # show ssh-configruation

find ~/.vagrant.d/ -type f -name Vagrantfile -exec grep -i pass {} \;   # default user and pwd for ubuntu-box



vagrant plugin install vagrant-vbguest
vagrant plugin update vagrant-vbguest
vagrant plugin repair vagrant-vbguest
```

## see also
- [[vagrantfile]]
- [[vboxmanage]]
- [16.04 - ubuntu xenial64 box password? - Ask Ubuntu](https://askubuntu.com/questions/832137/ubuntu-xenial64-box-password)
- [Multiple Vagrant VMs in One Vagrantfile](http://www.thisprogrammingthing.com/2015/multiple-vagrant-vms-in-one-vagrantfile/)
