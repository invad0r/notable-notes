---
tags: [coreutils, filesystem]
title: du
created: '2019-07-30T06:19:49.046Z'
modified: '2020-09-01T12:43:12.345Z'
---

# du

> `disk usage` estimates and displays the disk space used by files.

## usage
```sh
# options:
#    -c      Display a grand total
#    -h      "Human-readable" output.  Use unit suffixes: Byte, Kilobyte, Megabyte, Gigabyte, Terabyte and Petabyte.
#    -k      Sizes in kilobytes (default)
#    -s      Display only a total for each argument
#    -s      Display an entry for each specified file.  (Equivalent to -d 0)
#
# If the environment variable BLOCKSIZE is set, and the -k option is not specified,
# the block counts will be displayed in units of that size block.
# If BLOCKSIZE is not set, and the -k option is not specified, the block counts will be displayed in 512-byte blocks.

du -sk ./* | sort -nr       # total in kb

du -chsh ./*

du -chsh aufs/diff/* | sort -rk 1 | head -20    # top 20 largest file

du -s * | awk '{sum+=$1} END {print sum}'         # sum up disk usage

du -hst                                           # sum up disk usage

du -a . | sort -n -r | head -n 10                 # list-top-10-biggest-directories

tar cf - /folder-with-big-files -P | pv -s $(du -sb /folder-with-big-files | awk '{print $1}') | gzip > big-files.tar.gz


# measure-disk-space-of-certain-file-types-in-aggregate
for i in $(find . -type f | perl -ne 'print $1 if m/\.([^.\/]+)$/' | sort -u); do \
  cho "$i"": ""$(du -hac **/*."$i" | tail -n1 | awk '{print $1;}')";
done | sort -h -k 2 -r
```

## see also
- [[df]]
- [[sort]]
- [[tar]]
- [[gzip]]
- [[pv]]
