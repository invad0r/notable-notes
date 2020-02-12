---
tags: [linux, macos]
title: sysctl
created: '2019-07-30T06:19:49.249Z'
modified: '2020-02-04T12:28:35.409Z'
---

# sysctl 

> configure kernel parameters at runtime 

## usage
```sh
sysctl -a                             # print all

sysctl vm.swappiness                  # get single value

sysctl -n, --values                   # print only values of a variables
sysctl -n machdep.cpu.brand_string    # get cpu infor on macos: "Intel(R) Core(TM) i7-4980HQ CPU @ 2.80GHz"

sysctl –w {variable-name=value}       # Modify kernel parameter temporarily

sysctl -w vm.max_map_count=262144

cat /proc/sys/vm/swappiness           # same single value
```

## config
```sh
/etc/sysctl.conf              # where sysctl values are loaded at boot time  - modify Kernel parameter for permanent change

sysctl -p, --load[=<file>]    # read values from file
```

## see also
- [[dmesg]]
