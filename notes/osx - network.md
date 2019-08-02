---
tags: [osx]
title: osx - network
created: '2019-07-30T06:19:49.196Z'
modified: '2019-07-30T06:43:25.123Z'
---

# osx - network


```sh
ln -s /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport /usr/local/bin/airport

airport -s      # Scan for Wi-Fi networks

airport -c CHANNEL # Change channel

airport -z      # Disconnect

airport -I      # Get current connection info


```

```sh
networksetup -listallhardwareports


networksetup -listnetworkserviceorder

networksetup -listpreferredwirelessnetworks en0

networksetup -setairportpower en0 [on|off]

networksetup -setairportnetwork en0 SSID

networksetup -setairportnetwork devicename network [password]
```
