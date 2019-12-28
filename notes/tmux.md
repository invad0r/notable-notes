---
tags: [linux]
title: tmux
created: '2019-07-30T06:19:49.253Z'
modified: '2019-12-10T07:03:07.732Z'
---

# tmux

> `terminal multiplexer` enables a number of terminals to be created, accessed, and controlled from a single screen

```sh
:set status-style "bg=red"

:source-file ~/.tmux.conf         # reloadload .tmux.conf withough killing tmux session

tmux source-file ~/.tmux.conf

# show options
tmux show-options -g    # global
tmux show-options -w    # window
tmux show-options -s    # server
```

<kbd>C-b + :</kbd> - prompt

## windows (tabs) / panes
<kbd>C-b + ?</kbd>    - show keybindings
<kbd>C-b + &</kbd>    - kill window
<kbd>C-b + x</kbd>    - kill pane
<kbd>C-b + c</kbd>    - new window
<kbd>C-b + ,</kbd>    - name window
<kbd>C-b + w</kbd>    - list windows
<kbd>C-b + f</kbd>    - find window
<kbd>C-b + &</kbd>    - kill window

<kbd>C-b + .</kbd>    - move window - prompted for a new number

```sh
:movew                      # move window to the next unused number
:swap-window -s 1 -t 0      # swap -source to -target
:swap-window -t -1          # swap current window with next
```

<kbd>C-b + %</kbd> - horizontal split
<kbd>C-b + "</kbd> - vertical split

<kbd>C-b + o</kbd> - swap panes
<kbd>C-b + q</kbd> - show pane numbers
<kbd>C-b + x</kbd> - kill pane
<kbd>C-b + ⍽</kbd> - space - toggle between layouts
### join-pane
```
:join-pane -t :1      # moves current pante to window target 1

tmux join-pane -s 7 -t 6   # move window 7 as pane to window 6
```


## custom session
```sh
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

## see also
- [tmux cheatsheet](https://devhints.io/tmux) 
- [Moving tmux pane to window - unix.stackexchange.com](https://unix.stackexchange.com/questions/14300/moving-tmux-pane-to-window)
