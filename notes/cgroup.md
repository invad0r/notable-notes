---
tags: [container, linux]
title: cgroup
created: '2020-02-26T12:44:48.090Z'
modified: '2023-04-11T20:23:05.675Z'
---

# cgroup

## install

```sh
yum install libcgroup libcgroup-tools
```

## usage

```sh
lssubsys -am    # show all subsystems (unmounted ones) and mountpoints

CGROUP_ID="cgroup_$(shuf -i 1000-2000 -n 1)"

cgcreate -g "cpu,cpuacct,memory:$CGROUP_ID"
cgset -r cpu.share=512 "$CGROUP_ID"
cgset -r memory.limit_in_bytes=1000000000 "$CGROUP_ID"
cgexec -g "cpu,cpuacct,memory:$CGROUP_ID" \
  unshare "-fmuipn --mount-proc" \
  chroot "$PWD" \
  /bin/sh -c "/bin/mount -t proc proc /proc && hostname container-fun-times && /usr/bin/fish"
```

## see also

- [[docker]]
- [[container]]
- [twitter.com/b0rk/status/1230606332681691136](https://twitter.com/b0rk/status/1230606332681691136)
