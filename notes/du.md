---
tags: [linux]
title: du
created: '2019-07-30T06:19:49.046Z'
modified: '2019-07-30T07:10:26.067Z'
---

# du

`disk usage` estimates and displays the disk space used by files.

```sh
du file   

du -sk
# -s      Display an entry for each specified file.  (Equivalent to -d 0)
# -k      Display block counts in 1024-byte (1-Kbyte) blocks.

# If the environment variable BLOCKSIZE is set, 
# and the -k option is not specified, 
# the block counts will be displayed in units of that size block.  
# If BLOCKSIZE is not set, and the -k option is not specified, 
# the block counts will be displayed in 512-byte blocks.
````
```sh
du -chsh ./*

# -c      Display a grand total
# -h      "Human-readable" output.  Use unit suffixes: Byte, Kilobyte, Megabyte, Gigabyte, Terabyte and Petabyte.
# -s      Display an entry for each specified file.  (Equivalent to -d 0)


du -chsh aufs/diff/* | sort -rk 1 | head -20    # top 20 largest file


du -s * | awk '{sum+=$1} END {print sum}'         # sum up disk usage
du -hst                                           # sum up disk usage
du -a . | sort -n -r | head -n 10                 # list-top-10-biggest-directories


tar cf - /folder-with-big-files -P | pv -s $(du -sb /folder-with-big-files | awk '{print $1}') | gzip > big-files.tar.gz

````
