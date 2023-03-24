---
tags: [linux]
title: pmap
created: '2019-12-11T11:14:55.135Z'
modified: '2023-03-22T08:02:41.286Z'
---

# pmap

> report memory map of a process

## usage

```sh
pmap PID

pmap -q -d PID      # strip pmap output of headers and footers

pmap -xx PID        # used to display everything the kernel provides



memtop() {
  {
    echo "_PID_ _Name_ _Mem_"
    for i in /proc/[0-9]*; do
      echo -e "${i##*/}\t$(<$i/comm)\t$(pmap -d "${i##*/}" | tail -1 | { read a b c mem d; echo $mem; })"
    done \
    | sort -nr -k3 | head -$((${LINES:-23} - 3 ))
  } | column -t
} 2>/dev/null
```

## see also

- [[procps]]
- [[lsof]]
- [[bash ulimit]]
- [[sysctl]]
