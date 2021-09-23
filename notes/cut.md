---
tags: [coreutils]
title: cut
created: '2020-01-26T16:58:23.384Z'
modified: '2021-06-08T05:32:54.641Z'
---

# cut

> remove sections from each line of files 

## usage

```sh
-d, --delimiter=DELIM     # use DELIM instead of TAB for field delimiter 
-f, --fields=LIST         # select only these fields; 
                          # also print any line that contains no delimiter character, 
                          # unless the -s option is specified
-s, --only-delimited      # do not print lines not containing delimiters 
```

```sh
cut -d ' ' -f 6-
```

## see also
- [[bash eval]]
