---
tags: [linux]
title: apt
created: '2019-07-30T20:20:43.614Z'
modified: '2019-08-02T07:39:15.247Z'
---

# apt

### used packages
```sh
apt install net-tools       # ifconfig, nslookup
apt install dnsutils        # dig
apt install iputils-ping    # ping
apt install iproute2        # ip
```

### repository commands
```sh
apt-key adv --keyserver keyserver.ubuntu.com --recv-keys DF7DD7A50B746DD4

add-apt-repository "deb https://download.srcclr.com/ubuntu stable/"
add-apt-repository ppa:ian-berke/ppa-drawers  # ppa

apt-get update
apt-get install pkg

add-apt-repository -r "deb https://download.srcclr.com/ubuntu stable/"

apt remove drawers
apt autoremove         # remove former dependencies
add-apt-repository -r ppa:ian-berke/ppa-drawers

# apt-cache
apt-cache madison rabbitmq-server

apt-cache showpkg

apt-cache policy
```

### search for packages ?!
```sh
#!/bin/bash

# declare -a arrayName=(...)
package=('cmake' 'valac' 'libgtk-3-dev' 'librest-dev' 'libjson-glib-dev' 'libnotify-dev' 'libcanberra-dev' 'libx11-dev' 'libwebkitgtk-3.0-dev' 'libsqlite3-dev' 'libxtst-dev' 'libpurple-dev' 'libgee-dev' 'libdbusmenu-gtk-dev' 'libgtksourceview-3.0-dev')

echo 'array Size:' ${#package[@]}

for i in "${package[@]}" do
  :
  echo $(apt-cache search $i | grep -E "^$i\s")
done
```
