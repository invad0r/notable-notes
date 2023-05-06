---
tags: [macos]
title: xcode-select
created: '2020-11-30T13:00:10.243Z'
modified: '2023-05-01T19:43:37.552Z'
---

# xcode-select

> manages active developer directory for Xcode and BSD tools

## option

```sh
-s PATH, --switch PATH    # sets the active developer directory to PATH
-p,      --print-path     # prints path to currently selected developer directory
-r,      --reset          # unsets any user-specified developer directory, developer directory will be found via the default search mechanism
-v,      --version        # prints xcode-select version information
         --install        # opens a user interface dialog to request automatic installation of the command line developer tools
```

## usage

```sh
xcode-select --print-path                                 # find out version of xcode being used by tools

xcode-select --switch /Applications/Xcode8.3.3/Xcode.app  # select default xcode for cli

xcode-select --install                                    # download and install xcode cli tools
```

## see also

- [[cc]]
- [[brew]]
- [[softwareupdate]]
