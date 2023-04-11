---
tags: [shell/bash/builtin]
title: bash history
created: '2019-08-02T06:42:37.603Z'
modified: '2022-04-27T14:24:08.446Z'
---

# bash history

> display or manipulate the history list

## option

```sh
-c           # clear the history list by deleting all of the entries
-d offset    # delete the history entry at position OFFSET. Negative offsets count back from the end of the history list
-a           # append history lines from this session to the history file
-n           # read all history lines not already read from the history file and append them to the history list
-r           # read the history file and append the contents to the history list
-w           # write the current history to the history file
-p           # perform history expansion on each ARG and display the result without storing it in the history list
-s           # append the ARGs to the history list as a single entry
```

## environment variables

```sh
HISTTIMEFORMAT                    # format-string strftime(3) to print the time stamp for each displayed history entry
HISTTIMEFORMAT='%F %T '

HISTFILE                          # alternative history-file defaults to `~/.bash_history`
unset HISTFILE                    # don't save to history

HISTFILESIZE=1000000          
HISTSIZE=1000000

HISTCONTROL
HISTCONTROL=ignorespace          # start command with space to not get saved
HISTCONTROL=ignoredups           # ignore duplicate liens
HISTCONTROL=ignoreboth           # ignore both above
```

## usage

```sh
shopt -s histappend      # don't overwrite history file after each session
shopt -s cmdhist         # force commands entered on more than one line to be adjusted to fit on only one for parsing

PROMPT_COMMAND='history -a'

history 1

# top 30 entries
history | awk '{print $2}' | sort | uniq -c | sort -rn | head -30 | \
  awk '!max{max=$1;}{r=""; i=s=100*$1/max; while(i-->0)r=r"#"; printf "%50s %5d %s %s",$2,$1,r,"\n";}'
```

## see also

- [[bash history expansion]]
- [[bash fc]]
- [[bash shopt]]
- [sanctum.geek.nz/arabesque/better-bash-history/](https://sanctum.geek.nz/arabesque/better-bash-history/)
- [stackoverflow.com/execute-command-without-keeping-it-in-history](https://stackoverflow.com/questions/8473121/execute-command-without-keeping-it-in-history)
