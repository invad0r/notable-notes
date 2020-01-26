---
tags: [linux, packagemanager]
title: dpkg
created: '2019-07-30T20:19:32.637Z'
modified: '2020-01-22T14:21:53.378Z'
---

# dpkg

> package manager for debian

## usage
```sh
dpkg -i package.deb     # install package

# dependency problems prevent configuration
apt install ./package.deb
apt --fix-broken install


dpkg -S $(which ip)   # find out package

dpkg -S free.         # find out package


# search in dpkg database
dpkg-query -S '/bin/ls'
dpkg-query -S 'passwd*'
dpkg-query --search '/path/to/file'
dpkg-query --search '/usr/bin/passwd'
dpkg-query --search '/etc/passwd'


dpkg -l | head -3       # find install packages

dpkg --list |grep "^rc" | cut -d " " -f 3 | xargs sudo dpkg --purge   # remove marked "rc"

# dpkg flags
# First letter -> desired package state ("selection state"):
#    u ... unknown
#    i ... install
#    r ... remove/deinstall
#    p ... purge (remove including config files)
#    h ... hold
# Second letter -> current package state:
#    n ... not-installed
#    i ... installed
#    c ... config-files (only the config files are installed)
#    u ... unpacked
#    f ... half-configured (configuration failed for some reason)
#    h ... half-installed (installation failed for some reason)
#    w ... triggers-awaited (package is waiting for a trigger from another package)
#    t ... triggers-pending (package has been triggered)
# Third letter -> error state (you normally shouldn't see a thrid letter):
#    r ... reinst-required (package broken, reinstallation required)


grep ^ /etc/apt/sources.list /etc/apt/sources.list.d/*     # list-all-repos

dpkg -r srcclr      # remove ?!
```

## see also
- [[packagemanagers]]
- [What do the various dpkg flags like 'ii' 'rc' mean? - Ask Ubuntu](http://askubuntu.com/a/18807)
