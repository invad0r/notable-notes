---
tags: [bsdmainutils]
title: column
created: '2020-07-27T11:16:40.585Z'
modified: '2020-09-03T08:56:13.072Z'
---

# column

> columnate lists

## usage
```sh
# -s      characters to be used to delimit columns for the -t option
#         default columns are delimited with whitespace or with the characters supplied by -s
# -t      determine the number of columns the input contains and create a table
# -c      output is formatted for a display columns wide
# -x      fill columns before filling rows

column FILE  -t -s "|"      # file containers lines like "foo|bar|baz"


CMD | column -t
```

## see also
- [[mount]]
- [[tput]]
- [[sort]]
