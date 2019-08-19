---
title: tmux
created: '2019-07-30T06:19:49.253Z'
modified: '2019-08-19T14:33:15.026Z'
---

# tmux

[tmux cheatsheet](https://devhints.io/tmux) 


```sh
:set status-style "bg=red"
```

## conf
```sh
C-b :source-file ~/.tmux.conf         # reloadload .tmux.conf withough killing tmux session

tmux source-file ~/.tmux.conf

# show options
tmux show-options -g    # global
tmux show-options -w    # window
tmux show-options -s    # server
```
## windows (tabs) / panes
```
C-b ?               # show keybindings
C-b &               # kill window
C-b x               # kill pane
C-b c               # new window
C-b ,               # name window
C-b w               # list windows
C-b f               # find window
C-b &               # kill window

C-b .               # move window - prompted for a new number
C-b :movew<CR>      # move window to the next unused number

swap-window -s 1 -t 0      # swap -source to -target
swap-window -t -1          # swap current window with next

C-b %               # horizontal split
C-b "               # vertical split

C-b o               # swap panes
C-b q               # show pane numbers
C-b x               # kill pane
C-b ⍽               # space - toggle between layouts
```
### join-pane
```
join-pane -t :1      # moves current pante to window target 1

tmux join-pane -s 7 -t 6   # move window 7 as pane to window 6
```
[Moving tmux pane to window - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/14300/moving-tmux-pane-to-window)


## custom session
```sh
#!/bin/bash

SESSION=session

tmux new-window -k -n b-g_monitor
tmux split-window -v -p 50
tmux select-pane -t 1
tmux split-window -v -p 50
tmux select-pane -t 3
tmux split-window -h -p 50
tmux send-keys -t ${window}.1 'window1' Enter
tmux send-keys -t ${window}.2 'docker service ls --filter name=mb-api-' Enter
tmux send-keys -t ${window}.3 'docker ps --filter name=mb-api' Enter
tmux set-window-option -t $SESSION:0 automatic-rename off

# all done. select starting window and get to work
#tmux select-window -t $SESSION:0
#tmux -2 attach -t $SESSION

function window1 {
	swarm-mode-connect dev
	watch -d 'for color in {blue,green}; do echo $color; docker service inspect mb-api-${color}_application --format="{{json .Spec.Labels.SERVICE_8080_TAGS}}"; echo; done'
}
```
