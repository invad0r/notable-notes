---
tags: [linux, network]
title: wget
created: '2019-07-30T06:19:49.266Z'
modified: '2022-02-17T15:11:15.546Z'
---

# wget

> non-interactive network downloader

## install

`apt-get install wget`, `yum install wget`

## usage

```sh
-q        # no stdout
-O        # redirect output to file 
-         # 'dash' -> stdout
```

```sh
wget -qO- URL | CMD

wget --quiet --tries=1 --spider http://localhost/
```

## see also

- [[curl]]
- [[nc]]
- [daniel.haxx.se/docs/curl-vs-wget](https://daniel.haxx.se/docs/curl-vs-wget.html)
