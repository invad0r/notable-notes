---
tags: [linux]
title: tr
created: '2019-07-30T06:19:49.255Z'
modified: '2020-01-24T12:14:59.278Z'
---

# tr

> translate characters

## usage
```sh
echo "string" | tr '[:upper:]' '[:lower:]'  # translate all upercase to lowercase

echo $PS1 | tr ':' '\n'

tr -d '\n'    # remove new line character \n


tr '[:upper:]' '[:lower:]' <<EOF    # print batch in lowercase
VARIABLE_A
VARIABLE_N
VARIABLE_X
EOF

```

## see also
- [[url encoding]]
- [[bash parameter expansion]]
