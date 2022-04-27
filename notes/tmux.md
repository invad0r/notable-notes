---
tags: [linux]
title: tmux
created: '2019-07-30T06:19:49.253Z'
modified: '2021-11-04T10:47:53.783Z'
---

# tmux

> `terminal multiplexer` enables a number of terminals to be created, accessed, and controlled from a single screen

## usage

```sh
-2CDlNuvV
-c SHELL_COMMAND
-f FILE
-L SOCKET_NAME
-S SOCKET_PATH 
-T features command FLAGS
```

```sh
tmux ls                         # list sessions
tmux list-sessions

tmux list-sessions | awk 'BEGIN{FS=":"}{print $1}' | xargs -n 1 tmux kill-session -t

tmux list-commands
tmux new -s myname              # start new session

tmux a -t 0                     # attach to target 0
tmux -2 attach -t $SESSION

tmux kill-session -t myname     # kill session
tmux kill-server                # kill the tmux server and clients and destroy all sessions



tmux source-file ~/.tmux.conf
:source-file ~/.tmux.conf         # reloadload .tmux.conf withough killing tmux session

tmux show-options -g              # show options: global
tmux show-options -w              # show options: window
tmux show-options -s              # show options: server

:set status-style "bg=red"

tmux join-pane -s 7 -t 6           # move window 7 as pane to window 6
:join-pane -t :1                   # moves current pane to window target 1


tmux new-window -k -n b-g_monitor
tmux split-window -v -p 50
tmux select-pane -t 1

tmux send-keys -t ${window}.2 'docker service ls --filter name=mb-api-' Enter

tmux set-window-option -t $SESSION:0 automatic-rename off

```

## commands

```sh
:movew                      # move window to the next unused number
:swap-window -s 1 -t 0      # swap -source SOURCE to -target TARGET
:swap-window -t -1          # swap current window with next
```

## shortcuts

```sh
⌃-b + :         # prompt for command
⌃-b + ?         # show keybindings

⌃-b + &         # kill window
⌃-b + x         # kill pane

⌃-b + c         # new window
⌃-b + ,         # name window
⌃-b + w         # list windows
⌃-b + f         # find window
⌃-b + &         # kill window
⌃-b + .         # move window - prompted for a new number

⌃-b + %         # horizontal split
⌃-b + "         #"# vertical split
⌃-b + o         # swap panes
⌃-b + q         # show pane numbers
⌃-b + x         # kill pane
⌃-b + ⍽         # space - toggle between layouts
```

## see also

- [[fzf]]
- [devhints.io/tmux](https://devhints.io/tmux)
- [unix.stackexchange.com/questions/14300/moving-tmux-pane-to-window](https://unix.stackexchange.com/questions/14300/moving-tmux-pane-to-window)
- [[macos keyboard shortcuts]]
