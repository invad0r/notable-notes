---
tags: [shell/bash/builtin]
title: bash bind
created: '2019-08-02T06:42:37.558Z'
modified: '2023-05-28T16:56:23.007Z'
---

# bash bind

> set readline key bindings and variables / enable key macros

## option

```sh
-m KEYMAP                 # use KEYMAP as the keymap for the duration of command. keymap-names: emacs, emacs-standard, emacs-meta, emacs-ctlx, vi, vi-move, vi-command, vi-insert
-l                        # list names of functions
-P                        # list function names and bindings
-p                        # list functions and bindings in a form that can be reused as input
-S                        # list key sequences that invoke macros and their values
-s                        # list key sequences that invoke macros and their values in a form that can be reused as input
-V                        # list variable names and values
-v                        # list variable names and values in a form that can be reused as input
-q function-name          # query about which keys invoke the named function
-u function-name          # unbind all keys which are bound to the named function
-r KEYSEQ                 # remove the binding for KEYSEQ
-f FILENAME               # read key bindings from FILENAME
-x keyseq:shell-command   # cause SHELL-COMMAND to be executed when KEYSEQ is entered
-X                        # list key sequences bound with -x and associated commands in a form that can be reused as input
```

## usage

```sh
bind -X       # list key sequences bound with -x and associated commands

bind '"\e[24~":"foobar"'    # F12, prints "foobar" on cli ready for further editing
bind '"\e[24~":"pwd\n"'     # keystroke to enter a command immediately add linebreak at end
```

## see also

- [[gnu readline]]
- [stackoverflow.com/in-bash-how-do-i-bind-a-function-key-to-a-command](https://stackoverflow.com/questions/4200800/in-bash-how-do-i-bind-a-function-key-to-a-command)
