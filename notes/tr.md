---
tags: [linux]
title: tr
created: '2019-07-30T06:19:49.255Z'
modified: '2019-08-20T07:20:01.242Z'
---

# tr

`translate characters`

```sh
echo "string" | tr '[:upper:]' '[:lower:]'  # translate all upercase to lowercase

echo $PS1 | tr ':' '\n'
```
