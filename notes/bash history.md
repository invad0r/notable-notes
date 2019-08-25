---
tags: [bash/builtin]
title: bash history
created: '2019-08-02T06:42:37.603Z'
modified: '2019-08-20T07:21:21.964Z'
---

# bash history

[[bash history expansion]], [[bash fc]], [[bash shopt]]

```sh
history -a      # append history lines from this session to the history file

history -c      # clear the history list by deleting all of the entries

history -r      # read the history file and append the contents to the history list
```

## shopt
```sh
shopt -s histappend       # don't overwrite history file after each session
```
