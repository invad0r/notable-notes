---
tags: [bsdmainutils]
title: column
created: '2020-07-27T11:16:40.585Z'
modified: '2022-05-30T06:34:02.410Z'
---

# column

> columnate lists

## option

```sh
-s        # characters to be used to delimit columns for the -t option (default: delimited with whitespace)
-t        # determine number of columns the input contains and create a table
-c        # output is formatted for a display columns wide
-x        # fill columns before filling rows
```

## usage

```sh
column FILE  -t -s "|"      # file containers lines like "foo|bar|baz"

column -s, -t               # delimiter ,

CMD | column -t
```

## see also

- [[mount]]
- [[tput]]
- [[sort]]
- [[awk]]
