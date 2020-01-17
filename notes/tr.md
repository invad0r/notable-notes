---
tags: [linux]
title: tr
created: '2019-07-30T06:19:49.255Z'
modified: '2020-01-16T08:06:54.436Z'
---

# tr

> `translate characters`

## usage
```sh
echo "string" | tr '[:upper:]' '[:lower:]'  # translate all upercase to lowercase

echo ${foo,,}   # all to lowercase
echo ${foo^^}   # all to upercase

echo $PS1 | tr ':' '\n'

tr -d '\n'    # remove new line character \n
```

## see also
- [[url encoding]]
- [[bash parameter expansion]]
