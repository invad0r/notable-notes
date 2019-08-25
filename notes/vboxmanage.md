---
tags: [virtualization]
title: vboxmanage
created: '2019-07-30T06:19:49.257Z'
modified: '2019-08-22T09:18:46.932Z'
---

# vboxmanage

```sh
vboxmanage list vms

vboxmanage list runningvms

vboxmanage list bridgedifs        # get ip of bridged box
```

# find out ip address
```sh
vboxmanage guestproperty get "web" "/VirtualBox/GuestInfo/Net/0/V4/IP"    # returns the first IP of NIC likely to be NAT 10.0.*.*

vboxmanage guestproperty enumerate "web" | grep -i ip                     # return full list of all available IPs
```

## start vbox headless
```sh
vboxmanage startvm ubuntu-16.04-server-amd64 --type headless

vboxmanage list runningvms

vboxmanage controlvm ubuntu-16.04-server-amd64 poweroff
```

## get vm mac address
```sh
vboxmanage showvminfo ubuntu-16.04-server-amd64 | grep -i mac
# NIC 1: MAC: 0800270933C0, Attachment: Bridged Interface 'eth0', Cable connected: ..

for i in {1..254}; do 
  ping -c 1 192.168.1.$i &       # refresh-arp
done    

nmap -sP 192.168.1.1/24 \

arp -a | grep -i 08:00:27:09:33:C0
# ? (192.168.1.155) at 08:00:27:09:33:c0 [ether] on eth0
```

## make snapshot
```sh
vboxmanage snapshot vm04-zca8 take snap1-before-upgrade
vboxmanage showvminfo vm04-zca8
vboxmanage snapshot vm04-zca8 restore snap1-before-upgrade
vboxmanage snapshot vm04-zca8 delete snap1-before-upgrade
```

## get vm ip
```sh
# scan for headleass virtualbox ip => used for ssh@ip
vm=$(vboxmanage list runningvms | awk '{print $1}' | tr -d \")

if [ $# -ne 1 ] && [ -z ${vm+x} ]; then
  echo $0: usage: myscript name
  exit 1
fi

nmap -sP 192.168.1.1/24 >/dev/null    # update arp-table

# get mac from said virtualbox
# awk $4+0 => force awk to interpret $4 field as number and anything after will be ignored
macStr=$(vboxmanage showvminfo $vm | grep -i mac | awk {'print $4'})

mac=$(sed -e 's/.\{2\}/&:/g;s/.$//' <<< $macStr)

ip=$(arp -a | grep -i ${mac: : -1} | awk {'print $2'})

echo "$vm : $ip"
```

### create vm
```sh
VM=$(VBoxManage list runningvms | cut -d'"' -f2)
# VBoxManage showvminfo ${VM}

VBoxManage createvm --name $VM_NAME --register

VBoxManage modifyvm $VM_NAME \
  --ostype $VM_OSTYPE \
  --cpus $VM_CPUS \
  --memory $VM_MEM \
  --rtcuseutc on \
  --acpi on \
  --ioapic on \
  --hpet on \
  --hwvirtex on \
  --vtxvpid on \
  $TXUX_SUPPORT \
  --largepages on \
  --nestedpaging on \
  --firmware bios \
  --bioslogofadein off --bioslogofadeout off --bioslogodisplaytime 0 --biosbootmenu disabled \
  --boot1 dvd0

# ps aux | grep virtualbox
#/Applications/VirtualBox.app/Contents/MacOS/VBoxNetDHCP \
#  --ip-address 192.168.99.2 \
#  --lower-ip 192.168.99.100 \
#  --mac-address 08:00:27:56:B3:08 \
#  --netmask 255.255.255.0 \
#  --network HostInterfaceNetworking-vboxnet0 \
#  --trunk-name vboxnet0 \
#  --trunk-type netadp \
#  --upper-ip 192.168.99.254
```

## see also
- [Create VirtualBox VM from cli](https://www.perkin.org.uk/posts/create-virtualbox-vm-from-the-command-line.html)
- [Chapter8 VBoxManage](https://www.virtualbox.org/manual/ch08.html)
- [dotfiles/boot2docker magicmonty/dotfiles](https://github.com/magicmonty/dotfiles/blob/master/bin/boot2docker)
- [VirtualBox snapshots using the CLI – Dirk-Jan's blog](http://www.vleeuwen.net/2012/12/virtualbox-snapshots-using-the-cli)
