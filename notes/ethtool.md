---
tags: [linux, network]
title: ethtool
created: '2019-09-03T12:00:55.754Z'
modified: '2019-09-03T12:04:01.178Z'
---

# ethtool

```sh
ethtool           # Query or control network driver and hardware settings
ethtool -g eth0   # Display ring buffer for eth0
ethtool -i eth0   # Display driver information for eth0
ethtool -p eth0   # Identify eth0 by sight, typically by causing LEDs to blink on the network port
ethtool -S eth0   # Display network and driver statistics for eth0
```

## see also
- [[ip]]
