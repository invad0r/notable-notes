---
tags: [brew]
title: xargs
created: '2019-07-30T06:19:49.266Z'
modified: '2019-07-30T07:05:48.488Z'
---

# xargs


### install
`brew install findutils` (as `gxargs`)
[macos - Replacement for xargs -d in osx - Super User](https://superuser.com/questions/467176/replacement-for-xargs-d-in-osx)

### replace string
```sh
echo 210 | xargs -I {} bash -c "if [[ "{}" =~ 2 ]]; then echo {}; fi"
```
