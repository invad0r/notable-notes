---
tags: [iac]
title: vagrant
created: '2019-07-30T06:19:49.078Z'
modified: '2022-01-13T14:13:06.781Z'
---

# vagrant

> cli utility for managing the lifecycle of virtual machines

## install

`brew install vagrant`

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

## Vagrantfile

```sh
vagrant init
```

```ruby
Vagrant.configure(2) do |config|
	config.vm.box = "chef/centos-6.5"         # Specifying the box we wish to use
	config.vm.network "public_network"        # Adding Bridged Network Adapter

	(1..3).each do |i|                              # Iterating the loop for three times
		config.vm.define "edureka_vm#{i}" do |node|   # Defining VM properties
			config.vm.provider "virtualbox" do |node|   # Specifying the provider as VirtualBox and naming the VM's	
				node.name = "edureka_vm#{i}"              # The VM will be named as edureka_vm{i}
			end
		end
	end

end
```

```ruby
Vagrant.configure("2") do |config|
   config.vm.box = "opensuse/Leap-15.3.x86_64"
   config.vm.hostname = "k3s-server"
   config.vm.network "private_network", ip: "192.168.56.10"

   config.vm.provider "virtualbox" do |vb|
      vb.memory = "4096"
      vb.cpus = 2
      vb.customize ["modifyvm", :id, "--ioapic", "on"]
   end

   config.vm.provision "shell", inline: <<-SHELL
      zypper update
      zypper --non-interactive install curl command-not-found vim netcat-openbsd
   SHELL
end
```


```ruby
BOX_IMAGE = "bento/ubuntu-16.04"
NODE_COUNT = 2

Vagrant.configure("2") do |config|
  config.vm.define "master" do |subconfig|
    subconfig.vm.box = BOX_IMAGE
  end
  
  (1..NODE_COUNT).each do |i|
    config.vm.define "node#{i}" do |subconfig|
      subconfig.vm.box = BOX_IMAGE
    end
  end
end
```

## see also

- [[ip]]
- [[ruby]]
- [[vboxmanage]]
- [skubuntu.com/questions/832137/ubuntu-xenial64-box-password](https://askubuntu.com/questions/832137/ubuntu-xenial64-box-password)
- [thisprogrammingthing.com/2015/multiple-vagrant-vms-in-one-vagrantfile](http://www.thisprogrammingthing.com/2015/multiple-vagrant-vms-in-one-vagrantfile/)
