---
tags: [macos, network]
title: airport
created: '2019-07-30T06:19:49.196Z'
modified: '2022-02-02T08:49:57.619Z'
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
