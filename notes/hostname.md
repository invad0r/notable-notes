---
tags: [coreutils, net-tools]
title: hostname
created: '2019-09-26T09:09:44.806Z'
modified: '2023-05-15T13:23:36.951Z'
---

# hostname

> show or set the system's host name

## option

```sh
-f    # Include domain information, default behavior
-s    # trim off any domain information
-d    # only print domain information
```

## usage

```sh
hostname NEW_HOSTNAME   # change server hostname without a system restart

hostname -s             # print without fqdn


cat /etc/hostname

cat /etc/hosts
```

## see also

- [[hostnamectl]]
- [[host]]

