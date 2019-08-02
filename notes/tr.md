---
tags: [bash]
title: tr
created: '2019-07-30T06:19:49.255Z'
modified: '2019-07-30T07:09:23.317Z'
---

# tr

`translate characters`

```sh
echo "string" | tr '[:upper:]' '[:lower:]'  # translate all upercase to lowercase

echo $PS1 | tr ':' '\n'
```
