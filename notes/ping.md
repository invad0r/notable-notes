---
tags: [network]
title: ping
created: '2019-07-30T06:19:49.207Z'
modified: '2019-08-02T07:46:54.567Z'
---

# ping 

`Packet InterNet Groper`

* know whether a host is reachable from your network and how fast you get a response
* calculates the “Round Trip Time” (or RTT) that it takes a packet to reach a host

#### install
`apt install iputils-ping`

### examples
```sh
ping -c 5 192.168.1.5               # Stop after sending count

ping -s 100 -c 6 unixmen.com        # heavier packages

ping -i 3 unixmen.com               # increase interval 3 seconds

ping -i 0.2 unixmen.com             # decrease interval

ping -c 5 -q unixmen.com            # summary statistics

ping -w 6 unixmen.com               # timeout after 6 seconds
```

### ip notations
```sh
ping 0                      # linux: 127.0.0.1   osx: 0.0.0.0

ping 127.0                  # 127.0.0.1

ping 10.50.1                # 10.50.1

ping 10.0.513               # overflow: 2 x 256 + 1 shifts to the left


ping 167772673              # decimal notation

ping 0xa000201              # hex notation

ping 10.0.2.010             # octal notation
```
[There's more than one way to write an IP address](https://ma.ttias.be/theres-more-than-one-way-to-write-an-ip-address/)
