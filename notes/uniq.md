---
tags: [coreutils]
title: uniq
created: '2019-07-30T06:19:49.257Z'
modified: '2022-04-23T10:07:26.945Z'
---

# uniq

> report or filter out repeated lines in a file

## option

```sh
-c, --count                   # Precede each line with count of number of times line occurred in the input
-d, --repeated                # output a single copy of each line that is repeated in the input
-D, --all-repeated SEPTYPE    # output all lines that are repeated (like -d, but each copy of the repeated line is written).  
                              # optional SEPTYPE argument controls how to separate groups of repeated lines 
                              #    none     - Do not separate groups of lines (this is the default)
                              #    prepend  - Output an empty line before each group of lines
                              #    separate - Output an empty line after each group of lines
-f NUM, --skip-fields NUM     # Ignore first num fields in each input line
-i, --ignore-case             # case insensitive comparison of lines
-s chars, --skip-chars chars  # ignore the first chars characters in each input line when doing comparisons
-u, --unique                  # only output lines that are not repeated in the input
```

## usage

```sh
uniq -d file.txt    # prints only double entries, needs sort before !

uniq -c             # count
```

## see also

- [[sort]]
- [[wc]]
- [[ls]]
- [[awk]]
