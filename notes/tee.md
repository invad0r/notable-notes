---
tags: [linux]
title: tee
created: '2019-07-30T06:19:49.251Z'
modified: '2020-01-22T15:27:05.796Z'
---

# tee

> tee -- pipe fitting

## usage
```sh
CMD | tee file.log   # print to stdout and to file

# redirecting from tee to multiple files
CMD | tee >(jq -r .data > data.json) >(jq -r .id > id.json) >(jq -r .user > user.json)
```

## see also
- [[bash redirects]]
- [[jq]]
- [[vault]]
- [[bash process substitution]]
