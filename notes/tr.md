---
tags: [linux]
title: tr
created: '2019-07-30T06:19:49.255Z'
modified: '2019-09-04T06:13:25.723Z'
---

# tr

> `translate characters`

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
