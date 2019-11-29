---
tags: [json]
title: jo
created: '2019-07-30T06:19:49.120Z'
modified: '2019-08-28T22:25:06.709Z'
---

# jo

> small utility to create JSON objects

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
- [github.com/jpmens/jo](https://github.com/jpmens/jo)
