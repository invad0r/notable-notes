---
tags: [linux, macos]
title: qrencode
created: '2019-12-29T18:42:05.637Z'
modified: '2020-02-04T12:21:27.544Z'
---

# qrencode

> encode input data in a qr-code and save as a image

## install
`brew install qrencode`

## usage
```sh
qrencode        -o wifi.png "WIFI:T:WPA;S:<SSID>;P:<PASSWORD>;;"

qrencode -t SVG -o wifi.svg "WIFI:S:${SSID};T:WPA2;P:${SSID_PASS};;"
```

## see also
- [encoding-wifi-access-point-passwords-qr-code](https://feeding.cloud.geek.nz/posts/encoding-wifi-access-point-passwords-qr-code/)
