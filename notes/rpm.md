---
tags: [linux, packagemanager]
title: rpm
created: '2019-07-30T20:39:42.276Z'
modified: '2020-02-03T12:27:31.975Z'
---

# rpm

> `redhat package manager`

## usage
```sh
rpm -qa		              # list installed packages

rpm -i pkg	            # install

rpm -e pkg              # remove

rpm -qf $(which ip)     # find out package

rpm -ql bash            # find file and libraries provided by a particular package

curl -O http://mirror.centos.org/centos/6/os/x86_64/Packages/yum-3.2.29-81.el6.centos.noarch.rpm

rpm -ivh yum-3.2.29-81.el6.centos.noarch.rpm    # install
# if  "error: Failed dependencies:" download packages and install

rpm -qpR yum-3.2.29-81.el6.centos.noarch.rpm    # get dependency list
```

## see also
- http://mirror.centos.org/centos/7/os/x86_64/Packages/
- [[yum]]
- https://www.thegeekdiary.com/how-to-find-which-rpm-package-provides-a-specific-file-or-library-in-rhel-centos/
