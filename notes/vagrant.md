---
tags: [iac]
title: vagrant
created: '2019-07-30T06:19:49.078Z'
modified: '2019-10-23T14:30:49.587Z'
---

# vagrant

> command line utility for managing the lifecycle of virtual machines

## usage
```sh
vagrant init

vagrant box add chef/centos-6.5

vagrant box list

vagrant ssh-config    # show ssh-configruation

find ~/.vagrant.d/ -type f -name Vagrantfile -exec grep -i pass {} \;   # default user and pwd for ubuntu-box
```

## vagrantfile
```ruby
Vagrant.configure(2) do |config|
	config.vm.box = "chef/centos-6.5"         # Specifying the box we wish to use
	config.vm.network "public_network"        # Adding Bridged Network Adapter
	(1..3).each do |i|                        # Iterating the loop for three times
		config.vm.define "edureka_vm#{i}" do |node|   # Defining VM properties
			config.vm.provider "virtualbox" do |node|   # Specifying the provider as VirtualBox and naming the VM's	
				node.name = "edureka_vm#{i}"              # The VM will be named as edureka_vm{i}
			end
		end
	end
end
```

## see also
- [16.04 - ubuntu xenial64 box password? - Ask Ubuntu](https://askubuntu.com/questions/832137/ubuntu-xenial64-box-password)
- [Multiple Vagrant VMs in One Vagrantfile](http://www.thisprogrammingthing.com/2015/multiple-vagrant-vms-in-one-vagrantfile/)
