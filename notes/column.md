---
tags: [bsdmainutils]
title: column
created: '2020-07-27T11:16:40.585Z'
modified: '2021-06-08T05:31:43.739Z'
---

# column

> columnate lists

## usage

```sh
-s        # characters to be used to delimit columns for the -t option (default: delimited with whitespace)
-t        # determine number of columns the input contains and create a table
-c        # output is formatted for a display columns wide
-x        # fill columns before filling rows
```

```sh
column FILE  -t -s "|"      # file containers lines like "foo|bar|baz"

column -s, -t               # delimiter ,

CMD | column -t
```

## see also
- [[mount]]
- [[tput]]
- [[sort]]
