---
tags: [linux]
title: tmux
created: '2019-07-30T06:19:49.253Z'
modified: '2023-05-06T14:54:21.253Z'
---

# tmux

> `terminal multiplexer` enables a number of terminals to be created, accessed, and controlled from a single screen

```sh
multiplexer

A device that interleaves several activities; a switching device.
(computing, telecommunications) A device that combines several input signals into a single output sign

 ┌──────┐      ┌──────────┬──────────┬───────────┬────────────┐
 │      │      │          │          │           │   pane     │
 │      │      │          │          │           ├────────────┤
 │      │      │          │ session  │  window   │   pane     │
 │      │      │          │          │           ├────────────┤
 │      │attach│          │          │           │   pane     │
 │client├─────►│  server  ├──────────┼───────────┼────────────┤
 │      │      │          │          │           │   pane     │
 │      │      │          │          │  window   ├────────────┤
 │      │      │          │ session  │           │   pane     │
 │      │      │          │          ├───────────┼────────────┤
 │      │      │          │          │  window   │   pane     │
 └──────┘      └──────────┴──────────┴───────────┴────────────┘
```

## config

```sh
/opt/homebrew/etc/tmux.conf
$HOME/.tmux.conf
$XDG_CONFIG_HOME/tmux/tmux.conf 
$HOME/.config/tmux/tmux.conf
```

## option

```sh
-2              # force tmux to assume the terminal supports 256 colours, equivalent to -T 256
-C              # start in control mode, Given twice (-CC) disables echo
-c CMD          # execute shell command using default shell. option is for compatibility with sh(1) when tmux is used as a login shell
-D              # do not start the tmux server as a daemon.  This also turns the exit-empty option off.  With -D, command may not be specified
-f file         # alternative configuration file
-L socket-name  # allows a different socket name to be specified, allowing several independent tmux servers to be run
-l              # Behave as a login shell.  This flag currently has no effect and is for compatibility with other shells when using tmux as a login shell
-N              # Do not start the server even if the command would normally do so (for example new-session or start-server)
-S socket-path  # Specify a full alternative path to the server socket.  If -S is specified, the default socket directory is not used and any -L flag is ignored
-u              # write UTF-8 output even if the first environment variable of LC_ALL, LC_CTYPE, or LANG that is set does not contain "UTF-8" or "UTF8", equivalent to -T UTF-8
-T features     # set terminal features for the client
-v              # verbose logging
-V              # tmux version
```

## usage

```sh
tmux    CMD     # run CMD via tmux cli
C-b + : CMD     # run CMD in tmux command prompt 

        CMD -?  # short info about CMD
```

```sh
list-keys       lsk   [-1aN][-P prefix-string] [-T key-table] [key]
list-commands   lscm        [-F format] [command]

list-sessions   ls          [-F format] [-f filter]
list-windows    lsw   [-a]  [-F format] [-f filter] [-t target-session]
list-panes      lsp   [-as] [-F format] [-f filter] [-t target-window]

list-buffers    lsb         [-F format] [-f filter]
list-clients    lsc         [-F format] [-t target-session]
```

```sh
source-file ~/.tmux.conf   # reloadload .tmux.conf withough killing tmux session

tmux list-sessions | awk 'BEGIN{FS=":"}{print $1}' | xargs -n 1 tmux kill-session -t

tmux new -s myname              # start new session

tmux a -t 0                     # attach to target 0
tmux -2 attach -t $SESSION

kill-session -t myname     # kill session
kill-server                # kill the tmux server and clients and destroy all sessions


# there are three distinct classes of options: server, session, and window
# these classes are exclusive: each option belongs to only one of the classes
# there is never any inheritance between the option classes
show-options -s              # show options: server
show-options -g              # show options: global
show-options -w              # show options: window

set status-style "bg=red"



new-window -k -n b-g_monitor
split-window -v -p 50
select-pane -t 1

send-keys -t ${window}.2 'docker service ls --filter name=mb-api-' Enter

set-window-option -t $SESSION:0 automatic-rename off

movew                      # move window to the next unused number
swap-window -s 1 -t 0      # swap -source SOURCE to -target TARGET
swap-window -t -1          # swap current window with next


join-pane -s 7 -t 6           # move window 7 as pane to window 6
join-pane -t :1               # moves current pane to window target 1
```

## keybindings / shortcuts

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
- [[freedesktop xdg]]
- [[macos keyboard shortcuts]]
- [devhints.io/tmux](https://devhints.io/tmux)
- [unix.stackexchange.com/questions/14300/moving-tmux-pane-to-window](https://unix.stackexchange.com/questions/14300/moving-tmux-pane-to-window)
- [superuser.com/questions/758843/difference-between-global-server-session-and-window-options](https://superuser.com/questions/758843/difference-between-global-server-session-and-window-options)
