---
tags: [dsl]
title: awk function
created: '2020-01-03T07:42:16.401Z'
modified: '2020-09-02T12:52:42.764Z'
---

# awk function

## usage
```sh
printf "%10.0f\n" 1.28071e+09                     # print scientific notation as float to stdout

var = fprintf("%s %d %.2f\n", "Testing", 1, 3) }  # assigns its output to a variable, not stdout

split($1,swm,".");                                # split $1 into array swm[] with optional seperator "."

substr("foobar", 2, 3)                            # => "oob"

substr("foobar", 4)                               # => "bar"

length("foo")                                     # => 3

tolower("FOO")                                    # => "foo"

toupper("foo")                                    # => "FOO"

gsub(/"/, "")                                     # remove quotes globally
```

## see also
- [[awk]]
- [[awk variable]]
