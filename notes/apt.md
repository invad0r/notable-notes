---
tags: [linux, packagemanager]
title: apt
created: '2019-07-30T20:20:43.614Z'
modified: '2019-11-28T11:57:27.426Z'
---

# apt

## used packages 
package               | install
--                    | --
`ifconfig`, `nslookup`| `apt install net-tools`       
`dig`                 | `apt install dnsutils`        
`ping`                | `apt install iputils-ping`    
`ip`                  | `apt install iproute2`        


## usage
```sh
apt update

apt install FOO

apt remove FOO

apt autoremove         # remove former dependencies

apt list --installed
```

## apt-file - search for file/binary in packages
```sh
apt install apt-file

apt-file update

apt-file search mkpasswd
```

### repository commands
```sh
apt-key adv --keyserver keyserver.ubuntu.com --recv-keys DF7DD7A50B746DD4

add-apt-repository "deb https://download.srcclr.com/ubuntu stable/"
add-apt-repository -r "deb https://download.srcclr.com/ubuntu stable/"

add-apt-repository ppa:ian-berke/ppa-drawers  # ppa
add-apt-repository -r ppa:ian-berke/ppa-drawers
```

## see also
- [[apt-cache]]
- [[packagemanagers]]
- [[dig]]
- [[ping]]
- [[ip]]
