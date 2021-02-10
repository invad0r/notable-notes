---
title: xcode-select
created: '2020-11-30T13:00:10.243Z'
modified: '2020-11-30T13:03:40.743Z'
---

# xcode-select

> manages active developer directory for Xcode and BSD tools

## usage
```sh
xcode-select --print-path     # find out version of xcode being used by tools

xcode-select -switch /Applications/Xcode8.3.3/Xcode.app   # select default xcode for cli


xcode-select --install    # download and install xcode cli tools
```
## see also
- [[brew]]
