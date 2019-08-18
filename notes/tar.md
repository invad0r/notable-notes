---
tags: [linux]
title: tar
created: '2019-07-30T06:19:49.251Z'
modified: '2019-07-30T08:13:30.704Z'
---

# tar

> "Tape Archiver" is used to convert a group for file to an archive

```sh
tar cf - "$1" -P | pv -s $(( $(du -sk "$1" | cut -f1) * 1024 )) | gzip > "${1}.tar.gz"  # with progress
```

## create
```sh
tar cvzf archive_name.tar.gzip dirname/

  # c - create archive
  # v - verbose
  # z - filter the archive through gzip
  # f - archive filename
```
Note: `.tgz` is same as `.tar.gz`
```sh
tar cvfj archive-name.tar.bz2 dirname/

  # j – filter the archive through bzip2
```
Note: `.tbz` and `.tb2` is same as `.tar.bz2`

## extract / untar
```sh
tar xvf archive_name.tar
  # x - extract files from archive
```
## listing
```sh
tar tvf archive_name.tar
  # t - List archive contents to stdout.
```
## estimating
```sh
tar -czf - /directory/to/archive/ | wc -c
```
```sh
tar -cjf - /directory/to/archive/ | wc -c
```

## progress
```sh
tar cf - erl_crash.dump -P | \
  pv -s $(( $(du -sk erl_crash.dump | cut -f1) * 1024 )) | \
  gzip > erl_crash.dump.tar.gz
```
