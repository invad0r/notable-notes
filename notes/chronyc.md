---
tags: [linux]
title: chronyc
created: '2019-10-26T17:54:31.118Z'
modified: '2019-11-29T11:36:30.999Z'
---

# chronyc

> command-line interface for chrony daemon

## usage
```sh
chronyc -a makestep   # cancel any remaining correction that was being slewed and jump the system clock by the equivalent amount, making it correct immediately => update your system clock quickly 

chronyc tracking

chronyc sourcestats   # displays information about the drift rate and offset estimation process for each of the sources

chronyc sources -v    # displays information about the current time sources that chronyd is accessing

#   MS Name/IP address         Stratum Poll Reach LastRx Last sample
#   ===============================================================================
#   #* GPS0                          0   4   377    11   -479ns[ -621ns] +/-  134ns
#   ^? a.b.c                         2   6   377    23   -923us[ -924us] +/-   43ms
#   ^+ d.e.f                         1   6   377    21  -2629us[-2619us] +/-   86ms
#
#
#   M   indicates the mode of the source:
#       ^ means a server
#       = means a peer 
#       # indicates a locally connected reference clock
#   
#   S   state of the sources
#       * indicates the source to which chronyd is current synchronised. 
#       + indicates other acceptable sources. 
#       ? indicates sources to which connectivity has been lost. 
#       x indicates a clock which chronyd thinks is is a falseticker
#       ~ indicates a source whose time appears to have too much variability. shown at start-up, until at least 3 samples have been gathered from it
```

## see also
- [[chronyd]]
- https://blacksaildivision.com/ntp-centos
- https://docs.fedoraproject.org/en-US/Fedora/18/html/System_Administrators_Guide/sect-Checking_if_chrony_is_synchronized.html
