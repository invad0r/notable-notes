---
tags: [cli, iac]
title: hashicrop vagrant
created: '2019-07-30T06:19:49.078Z'
modified: '2019-08-18T15:00:40.784Z'
---

# hashicrop vagrant
```sh
vagrant box list
```  

## show ssh-configruation
```sh
vagrant ssh-config
```

## default user and pwd for ubuntu-box
```sh
find /Users/user/.vagrant.d/ -type f -name Vagrantfile -exec grep -i pass {} \;
```
[16.04 - ubuntu xenial64 box password? - Ask Ubuntu](https://askubuntu.com/questions/832137/ubuntu-xenial64-box-password)
[Multiple Vagrant VMs in One Vagrantfile](http://www.thisprogrammingthing.com/2015/multiple-vagrant-vms-in-one-vagrantfile/)

```sh
vagrant init

vagrant box add chef/centos-6.5
```

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
