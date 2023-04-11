---
tags: [coreutils]
title: tr
created: '2019-07-30T06:19:49.255Z'
modified: '2023-04-11T11:12:03.422Z'
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

- [[cut]]
- [[sed]]
- [[seq]]
- [[bash echo]]
- [[bash parameter expansion]]
