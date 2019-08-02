---
tags: [bash, linux, regex]
title: regex
created: '2019-07-30T06:19:49.223Z'
modified: '2019-07-30T18:46:01.299Z'
---

# regex

[Regular-Expressions.info - Regexp Patterns](https://www.regular-expressions.info/)

## flavors
|flavor| |
|--|--|
| `PCRE`            | Perl Compatible Regular Expressions (c library) |
| `ECAM/JavaScript` | |
| `java`            | |
| `POSIX BRE`       | Basic Regular Expressions IEEE POSIX standard 1003.2. |
| `POSIX ERE`       | Extended Regular Expressions as defined in the IEEE POSIX standard 1003.2. |
| `GNU BRE`         | GNU Basic Regular Expressions, which are POSIX BRE with GNU extensions     |
| `GNU ERE`         | GNU Extended Regular Expressions, which are POSIX ERE with GNU extensions  |


## tools

* grep [GNU Grep 3.0: Basic vs Extended](https://www.gnu.org/software/grep/manual/html_node/Basic-vs-Extended.html)
* find
  * `-name` uses pattern
  * `-regex`


## Patterns

```
[^="]++(?=")
```

