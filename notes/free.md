---
tags: [linux]
title: free
created: '2019-07-30T06:19:49.055Z'
modified: '2020-02-24T12:32:34.507Z'
---

# free

## install
`apt-get install procps`

## usage

```sh
free -h   # human readable

#              total        used        free      shared  buff/cache   available
# Mem:           7.8G        4.7G        152M         19M        3.0G        2.8G
# Swap:          2.8G        413M        2.4G
#
#
# total       Total installed memory (MemTotal and SwapTotal in /proc/meminfo)
# used        Used memory (calculated as total - free - buffers - cache)
# free        Unused memory (MemFree and SwapFree in /proc/meminfo)
# shared      Memory used (mostly) by tmpfs (Shmem in /proc/meminfo, on kernels 2.6.32, displayed as zero if not available)
# buff/cache  Sum of buffers and cache
#             buffers Memory used by kernel buffers (Buffers in /proc/meminfo)
#             cache   Memory used by the page cache and slabs (Cached and Slab in /proc/meminfo)
# available   Estimation of how much memory is available for starting new applications, without swapping. 
#             Unlike the data provided by the cache or free fields, this field takes into account page cache and also that not all reclaimable memory slabs will be reclaimed due to items being in use (MemAvailable in /proc/meminfo, available on kernels 3.14, emulated on kernels 2.6.27+, otherwise the same as free)
```

```sh
cat /proc/meminfo

sudo sync && sudo sh -c "echo 1 > /proc/sys/vm/drop_caches"     # clear memory cache
```

## see also
- [[procfs]]
- [[top]]
- [How to Clear RAM Memory Cache, Buffer and Swap Space on Linux](https://www.tecmint.com/clear-ram-memory-cache-buffer-and-swap-space-on-linux/)

