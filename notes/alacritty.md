---
title: alacritty
created: '2023-03-07T07:58:26.959Z'
modified: '2023-03-07T08:07:10.987Z'
---

# alacritty

> terminal emulator, sensible defaults, extensive configuration

## install

```sh
brew install alacritty

cargo install alacritty
```

## flags

```sh
    --class INSTANCE            # Defines window class/app_id on X11/Wayland [default: Alacritty]
    --config-file FILE          # alternative configuration file [default: $HOME/.config/alacritty/alacritty.yml]
-e, --command CMD...            # command and args to execute (must be last argument)
    --embed EMBED               # X11 window ID to embed Alacritty within (decimal or hexadecimal with "0x" prefix)
-h, --help                      # Print help information
    --hold                      # Remain open after child process exit
-o, --option OPT...             # override configuration file options [example: cursor.style=Beam]
    --print-events              # print all events to stdout
-q                              # reduces the level of verbosity (min level is -qq)
    --ref-test                  # generates ref test
    --socket SOCKET             # path for IPC socket creation
-t, --title TITLE               # defines the window title [default: Alacritty]
-v                              # increases the level of verbosity (the max level is -vvv)
-V, --version                   # print version information
    --working-directory DIR     # start shell in specified working directory
```

## usage

```sh
alacrity -v       # start session verbose 

alacrity help    # print help
alacrity msg     # send message to the Alacritty socket
```

## see also

- [[brew]]
- [[cargo]]
- [[tmux]]
- [[bash]]
