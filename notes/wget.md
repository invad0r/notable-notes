---
tags: [linux, network]
title: wget
created: '2019-07-30T06:19:49.266Z'
modified: '2019-12-10T14:46:19.397Z'
---

# wget

> non-interactive network downloader

## usage
```sh
wget -qO- URL | PROGRAMM
  # -q    - no stdout
  # -O    - redirect output to file 
  # -     - dash is the stdoutput

wget --quiet --tries=1 --spider http://localhost/
```

## see also
- [[curl]]
