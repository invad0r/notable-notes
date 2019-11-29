---
tags: [network, osx]
title: airport
created: '2019-07-30T06:19:49.196Z'
modified: '2019-11-28T11:53:02.808Z'
---

# airport

> get information for 802.11 interface

## usage
```sh
ln -s /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport /usr/local/bin/airport

airport -s      # Scan for Wi-Fi networks

airport -c CHANNEL # Change channel

airport -z      # Disconnect

airport -I      # Get current connection info
```

## see also
- [[networksetup]]
