---
title: jo
created: '2019-07-30T06:19:49.120Z'
modified: '2021-10-29T12:36:06.424Z'
---

# jo

> small utility to create JSON objects

## usage

```sh
array[1]=foo
array[2]=bar

jo -p -a ${array[@]}
```

```json
[
   "foo",
   "bar"
]
```

## see also

- [[jq]]
- [[yq]]
- [github.com/jpmens/jo](https://github.com/jpmens/jo)
