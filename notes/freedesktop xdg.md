---
tags: [Notebooks]
title: freedesktop xdg
created: '2023-04-26T11:21:25.119Z'
modified: '2023-04-26T11:37:42.670Z'
---

# freedesktop xdg

> Cross-Desktop Group 

## desktop base directories `basedir`

> defines location fo application configuration and data files

### xdg environment vairables 

```sh
XDG_CONFIG_HOME     # user-specific config files                  default $HOME/.config
XDG_DATA_HOME       # user-specific data files                    default $HOME/.local/share
XDG_STATE_HOME      # user-specific state data                    default $HOME/.local/state
XDG_CACHE_HOME      # user-specific non-essential (cached) data   default $HOME/.cache
XDG_RUNTIME_DIR     # runtime files bound to the login status of the user

# XDG_CONFIG_DIRS and XDG_DATA_DIRS can be used to define an ordered set of directories to search for their respective files, rather than just a single directory

# macos specific
XDG_CONFIG_HOME     # ~/Library/Preferences/ using reverse domain name notation: com.apple.AppStore.appname
XDG_DATA_HOME       # ~/Library/
XDG_CACHE_HOME      # ~/Library/Caches/
```

[specifications.freedesktop.org/basedir-spec](https://specifications.freedesktop.org/basedir-spec/latest/ar01s03.html)

## desktop entries `.desktop`

> defines executable, applicaiton name, icon and description used by app launchers and desktop menus

## see also

- [[alacrity]]
- [[tmux]]
- [[nvim]]
