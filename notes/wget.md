---
tags: [linux, network]
title: wget
created: '2019-07-30T06:19:49.266Z'
modified: '2022-11-23T10:13:22.767Z'
---

# wget

> non-interactive network downloader

## install

```
apt-get install wget
yum install wget
```

## flags

```sh
-q        # no stdout
-O        # redirect output to file 
-         # 'dash' -> stdout
```

## usage

```sh
wget -qO- URL | CMD

wget --quiet --tries=1 --spider http://localhost/
```

## see also

- [[curl]]
- [[nc]]
- [daniel.haxx.se/docs/curl-vs-wget](https://daniel.haxx.se/docs/curl-vs-wget.html)
