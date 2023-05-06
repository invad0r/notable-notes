---
tags: [shell/bash/builtin]
title: bash history
created: '2019-08-02T06:42:37.603Z'
modified: '2023-04-21T12:21:46.970Z'
---

# bash history

> display or manipulate the history list

## environment variables

```sh
man bash                      # get available env vars

HISTTIMEFORMAT                    # format-string strftime(3) to print the time stamp for each displayed history entry
HISTTIMEFORMAT='%F %T '           # => "10  2023-04-21            vi README.md"
HISTTIMEFORMAT='%F %T %t'         # => "10  2023-04-21 11:50:06   vi README.md"

HISTFILE                          # alternative history-file defaults to `~/.bash_history`
unset HISTFILE                    # don't save to history

HISTFILESIZE=1000000          
HISTSIZE=1000000

HISTCONTROL
HISTCONTROL=ignorespace          # start command with space to not get saved
HISTCONTROL=ignoredups           # ignore duplicate liens
HISTCONTROL=ignoreboth           # ignore both above



HISTCONTROL       # colon-separated list of values controlling how commands are saved on the history list.  
                  # If the list of values includes ignorespace, lines which begin with a space character are not saved in the history list.  A value of ignoredups causes lines matching the previous history entry to not be saved.  A value of ignoreboth is shorthand for ignorespace and ignoredups.  A value of erasedups causes all previous lines matching the current line to be removed from the history list before that line is saved.  Any value not in the above list is ignored.  If HISTCONTROL is unset, or does not include a valid value, all lines read by the shell parser are saved on the history list, subject to the value of HISTIGNORE.  The second and subsequent lines of a multi-line compound command are not tested, and are added to the history regardless of the value of HISTCONTROL.
HISTFILE          # filename in which command history is saved default value is ~/.bash_history. If unset history is not saved
HISTFILESIZE      # max number of lines contained in the history file.  When this variable is assigned a value, the history file is truncated, if necessary, to contain no more than that number of lines by removing the oldest entries.  The history file is also truncated to this size after writing it when a shell exits.  If the value is 0, the history file is truncated to zero size.  Non-numeric values and numeric values less than zero inhibit truncation.  The shell sets the default value to the value of HISTSIZE after reading any startup files.
HISTIGNORE        # colon-separated list of patterns used to decide which command lines should be saved on the history list.  Each pattern is anchored at the beginning of the line and must match the complete line (no implicit `*' is appended).  Each pattern is tested against the line after the checks specified by HISTCONTROL are applied.  In addition to the normal shell pattern matching characters, `&' matches the previous history line.  `&' may be escaped using a backslash; the backslash is removed before attempting a match.  The second and subsequent lines of a multi-line compound command are not tested, and are added to the history regardless of the value of HISTIGNORE.  The pattern matching honors the setting of the extglob shell option.
HISTSIZE          # number of commands to remember in the command history If the value is 0, commands are not saved in the history list
HISTTIMEFORMAT    # If variable is set and not null, its value is used as a strftime(3) to print the time stamp associated with each history entry displayed by the history builtin
```

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

- [[wc]]
- [[bash fc]]
- [[bash shopt]]
- [[bash redirect]]
- [[bash history expansion]]
- [sanctum.geek.nz/arabesque/better-bash-history/](https://sanctum.geek.nz/arabesque/better-bash-history/)
- [stackoverflow.com/execute-command-without-keeping-it-in-history](https://stackoverflow.com/questions/8473121/execute-command-without-keeping-it-in-history)
