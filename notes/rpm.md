---
tags: [linux, packagemanager]
title: rpm
created: '2019-07-30T20:39:42.276Z'
modified: '2019-09-17T12:02:28.286Z'
---

# rpm

> `redhat package manager`

## usage
```sh
rpm -qa		      # list

rpm -i pkg	    # install

rpm -e pkg      # remove
```

## find out package
```sh
rpm -qf $(which ip)

rpm -ql bash    # find file and libraries provided by a particular package
```

## see also
- [[packagemanagers]]
- [[yum]]
- https://www.thegeekdiary.com/how-to-find-which-rpm-package-provides-a-specific-file-or-library-in-rhel-centos/
