---
tags: [bash/builtin]
title: bash history
created: '2019-08-02T06:42:37.603Z'
modified: '2019-09-17T12:09:06.778Z'
---

# bash history

```sh
history -a      # append history lines from this session to the history file

history -c      # clear the history list by deleting all of the entries

history -r      # read the history file and append the contents to the history list
```

## don't save to history
```sh
unset HISTFILE      # don't save to history e.g. type in password

# or

export HISTCONTROL=ignorespace # then start command with space 
```

## shopt
```sh
shopt -s histappend       # don't overwrite history file after each session
```

## see also
- [[bash history expansion]]
- [[bash fc]]
- [[bash shopt]]
- https://stackoverflow.com/questions/8473121/execute-command-without-keeping-it-in-history
