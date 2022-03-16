---
tags: [linux]
title: pigz
created: '2020-01-22T13:43:00.526Z'
modified: '2022-02-02T09:32:20.505Z'
---

# pigz

> compress or expand files - multithreaded replacement for `gzip`
> pronounced `pig-zee` - It is not pronounced like the plural of pig

## compression levels

```sh
6     # default compression
1     # fastest, but offers least compression
9     # slowest, but best compression
0     # no compression
```

## usage

```sh
pigz -9 FILE    # compress FILE with level 9 to .gz and remove origial !

pigz -k FILE    # keep original FILE

pigz -l FILE    # list content of compressed FILE
```

## tar

pigz does not have options to compress a folder, it only compresses single files. 
As a workaround, [[pigz]] is used in conjunction with [[tar]] command to [[zip]] directories

```sh
tar cf - paths-to-archive | pigz -9 -p 32 > archive.tar.gz

tar -I pigz -xf archive.tar.gz -C /tmp    # fast unpack
tar -cf archive.tar.gz -I pigz /opt       # fast pack

tar --use-compress-program="pigz --best --recursive" -cf archive.tar.gz directory
tar --use-compress-program="pigz --best --recursive | pv" -cf archive.tar.gz directory    # monitor progresse
```

## see also

- [[zip]]
- [[tar]]
- [[gzip gunzip zcat]]
- [[pv]]
- [linux.die.net/man/1/pigz](https://linux.die.net/man/1/pigz)
