---
tags: [network, osx]
title: networksetup
created: '2019-09-06T06:34:44.756Z'
modified: '2019-09-06T06:36:44.629Z'
---

# networksetup

> configuration tool for network settings in System Preferences

```sh
networksetup -listallhardwareports

networksetup -listnetworkserviceorder

networksetup -listpreferredwirelessnetworks en0

networksetup -setairportpower en0 [on|off]

networksetup -setairportnetwork en0 SSID

networksetup -setairportnetwork devicename network [password]
```

## see also
- [[airport]]
