---
tags: [bash, bash/builtin]
title: bash shopt
created: '2019-07-30T06:19:49.237Z'
modified: '2019-08-02T06:51:22.430Z'
---

# bash shopt

> Historically, the set command was used to turn options on and off. As the number of options grew, set became more difficult to use because options are represented by single letter codes. As a result, Bash provides the `shopt` command to turn options on and off by name instead of a letter. 

### set-and-unset-shell-options:
```
  -s     set, enable
  -u     unset, disable
  -q     quite mode
  -p     print
```

```sh
shopt -p    # print all options
```
