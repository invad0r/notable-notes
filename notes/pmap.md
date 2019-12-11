---
title: pmap
created: '2019-12-11T11:14:55.135Z'
modified: '2019-12-11T11:15:24.761Z'
---

# pmap

## usage
```sh
memtop() {
  {
    echo "_PID_ _Name_ _Mem_"
    for i in /proc/[0-9]*; do
      echo -e "${i##*/}\t$(<$i/comm)\t$(pmap -d "${i##*/}" | tail -1 | { read a b c mem d; echo $mem; })"
    done \
    | sort -nr -k3 \
    | head -$((${LINES:-23} - 3 ))
  } | column -t
} 2>/dev/null

```
## see also
-
