---
tags: [linux, osx]
title: sysctl
created: '2019-07-30T06:19:49.249Z'
modified: '2019-07-30T09:04:53.791Z'
---

# sysctl 

configure kernel parameters at runtime 

```sh
sysctl -a   # print all


sysctl vm.swappiness          # get single value

cat /proc/sys/vm/swappiness   # same single value


/etc/sysctl.conf              # sysctl values are loaded at boot time from the 

vi /etc/sysctl.conf           # Modify Kernel parameter in /etc/sysctl.conf for permanent change
sysctl –p




sysctl –w {variable-name=value}  # Modify kernel parameter temporarily

sysctl -w vm.max_map_count=262144
```



## osx
```sh
sysctl -n machdep.cpu.brand_string

  # Intel(R) Core(TM) i7-4980HQ CPU @ 2.80GHz
```
