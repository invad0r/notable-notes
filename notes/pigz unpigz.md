---
title: pigz unpigz
created: '2020-01-22T13:43:00.526Z'
modified: '2020-01-22T14:02:40.455Z'
---

# pigz unpigz

> compress or expand files - multithreaded replacement for `gzip`
> pronounced `pig-zee` - It is not pronounced like the plural of pig

## usage
```sh
tar cf - paths-to-archive | pigz -9 -p 32 > archive.tar.gz

tar -I pigz -xf archive.tar.gz -C /tmp    # fast unpack
tar -cf archive.tar.gz -I pigz /opt     # fast pack

tar --use-compress-program="pigz --best --recursive" -cf archive.tar.gz directory
tar --use-compress-program="pigz --best --recursive | pv" -cf archive.tar.gz directory    # monitor progresse
```

## see also
- [[tar]]
- [[gzip gunzip zcat]]
- [[pv]]
- https://linux.die.net/man/1/pigz
