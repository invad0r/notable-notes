---
tags: [linux]
title: tmux
created: '2019-07-30T06:19:49.253Z'
modified: '2020-03-02T12:37:20.153Z'
---

# tmux

> `terminal multiplexer` enables a number of terminals to be created, accessed, and controlled from a single screen

## usage
```sh
tmux list-commands
tmux new -s myname              # start new session
tmux ls                         # list sessions

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
:join-pane -t :1                   # moves current pante to window target 1


tmux new-window -k -n b-g_monitor
tmux split-window -v -p 50
tmux select-pane -t 1

tmux send-keys -t ${window}.2 'docker service ls --filter name=mb-api-' Enter

tmux set-window-option -t $SESSION:0 automatic-rename off

:movew                      # move window to the next unused number
:swap-window -s 1 -t 0      # swap -source to -target
:swap-window -t -1          # swap current window with next
```

shortcut           | desc
--                 |--
<kbd>C-b + :</kbd> | prompt for command
<kbd>C-b + ?</kbd> | show keybindings
<kbd>C-b + &</kbd> | kill window
<kbd>C-b + x</kbd> | kill pane
<kbd>C-b + c</kbd> | new window
<kbd>C-b + ,</kbd> | name window
<kbd>C-b + w</kbd> | list windows
<kbd>C-b + f</kbd> | find window
<kbd>C-b + &</kbd> | kill window
<kbd>C-b + .</kbd> | move window - prompted for a new number
<kbd>C-b + %</kbd> | horizontal split
<kbd>C-b + "</kbd> | vertical split
<kbd>C-b + o</kbd> | swap panes
<kbd>C-b + q</kbd> | show pane numbers
<kbd>C-b + x</kbd> | kill pane
<kbd>C-b + ⍽</kbd> | space - toggle between layouts

## see also
- [tmux cheatsheet](https://devhints.io/tmux) 
- [Moving tmux pane to window - unix.stackexchange.com](https://unix.stackexchange.com/questions/14300/moving-tmux-pane-to-window)
