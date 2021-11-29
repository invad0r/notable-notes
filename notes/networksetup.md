---
tags: [macos, network]
title: networksetup
created: '2019-09-06T06:34:44.756Z'
modified: '2021-10-31T14:49:12.470Z'
---

# networksetup

> configuration tool for network settings in System Preferences

## usage

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
- [[nmap]]
- [[wireshartk]]
