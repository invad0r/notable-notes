---
tags: [linux, packagemanager]
title: apt
created: '2019-07-30T20:20:43.614Z'
modified: '2020-01-16T07:32:23.166Z'
---

# apt
> high-level commandline interface for the package management system

## usage
```sh
apt update

apt install FOO

apt remove FOO

apt autoremove         # remove former dependencies

apt list --installed
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
- [[apt-file]]
- [[apt-cache]]
- [[packagemanagers]]

