---
tags: [bash/built-in]
title: bash history
created: '2019-08-02T06:42:37.603Z'
modified: '2020-07-31T06:24:21.636Z'
---

# bash history

```sh
history -a      # append history lines from this session to the history file

history -c      # clear the history list by deleting all of the entries

history -r      # read the history file and append the contents to the history list

history 1


unset HISTFILE                    # don't save to history
export HISTCONTROL=ignorespace    # start command with space to not get saved


shopt -s histappend       # don't overwrite history file after each session
```

## see also
- [[bash history expansion]]
- [[bash fc]]
- [[bash shopt]]
- https://stackoverflow.com/questions/8473121/execute-command-without-keeping-it-in-history
