---
tags: [coreutils]
title: tee
created: '2019-07-30T06:19:49.251Z'
modified: '2020-09-01T12:43:12.523Z'
---

# tee

> `tee` - pipe fitting

## usage
```sh
CMD | tee file.log   # print to stdout and to file

# redirecting from tee to multiple files
CMD | tee >(jq -r .data > data.json) >(jq -r .id > id.json) >(jq -r .user > user.json)
```

## see also
- [[pee]]
- [[jq]]
- [[vault]]
- [[bash redirects]]
- [[bash process substitution]]
