---
tags: [initsystem, macos]
title: launchctl
created: '2019-09-04T14:00:13.320Z'
modified: '2022-02-04T08:25:05.512Z'
---

# launchctl

> Interfaces with launchd

## usage

```sh
launchctl load ~/Library/LaunchAgents/com.demo.daemon.plist

launchctl unload ~/Library/LaunchAgents/com.demo.daemon.plist

launchctl list
launchctl list homebrew.mxcl.mongodb@3.0

launchctl start

launchctl stop
```

## see also

- [[systemctl]]
- [[launchd]]
