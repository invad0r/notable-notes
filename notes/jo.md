---
tags: [json]
title: jo
created: '2019-07-30T06:19:49.120Z'
modified: '2023-03-22T10:41:34.223Z'
---

# jo

> small utility to create JSON objects

## usage

```sh
ARRAY[1]=foo
ARRAY[2]=bar

jo -p -a ${ARRAY[@]}
```

```json
[
   "foo",
   "bar"
]
```

## see also

- [[jq]]
- [[jsonnet]]
- [[yq]]
- [github.com/jpmens/jo](https://github.com/jpmens/jo)
