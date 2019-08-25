---
tags: [initsystem, linux, osx]
title: launchd
created: '2019-08-21T06:37:19.782Z'
modified: '2019-08-22T07:25:03.812Z'
---

# launchd

> service management framework for starting, stopping and managing daemons, applications, processes, and scripts. Introduced with Mac OS X Tiger and is licensed under the Apache License.

```sh
launchctl load ~/Library/LaunchAgents/com.demo.daemon.plist

launchctl unload ~/Library/LaunchAgents/com.demo.daemon.plist
```

## see also
- [launchd.info](https://www.launchd.info/)
