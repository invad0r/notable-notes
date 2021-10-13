---
tags: [macos]
title: xcode-select
created: '2020-11-30T13:00:10.243Z'
modified: '2021-09-30T07:06:24.548Z'
---

# xcode-select

> manages active developer directory for Xcode and BSD tools

## usage

```sh
xcode-select --print-path                                 # find out version of xcode being used by tools

xcode-select -switch /Applications/Xcode8.3.3/Xcode.app   # select default xcode for cli

xcode-select --install                                    # download and install xcode cli tools
```

## see also

- [[brew]]
- [[softwareupdate]]
