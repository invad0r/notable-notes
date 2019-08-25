---
tags: [awk, linux]
title: awk
created: '2019-07-30T06:19:48.989Z'
modified: '2019-08-25T20:00:14.758Z'
---

# awk

> initially developed in 1977 by `A`lfred Aho, Peter `W`einberger, and Brian `K`ernighan

### implementations
```
nawk       #  “new awk”, an evolution of oawk, the original UNIX implementation, used on *BSD and widely available on Linux
mawk       #  a fast implementation that mostly sticks to standard features
gawk       #  the GNU implementation, with many extensions
Busybox    #  small, intended for embedded systems, not many features
````
```sh
awk -f        # Read the AWK program source from file

awk -F        # Field Seperator
```

### Built-in Variables
```
# 1. Type: Variable which defines values which can be changed such as field separator and record separator.

# 2. Type: Variable which can be used for processing and reports such as Number of records, number of fields.

FS          # Input field separator variable

OFS         # Output Field Separator Variable

RS          # Record Separator variable

ORS         # Output Record Separator Variable

NR          # Number of Records Variable / aka line

NF          # Number of Fields in a record / aka $1 $2 ..

FILENAME    # Name of the current input file

FNR         # Number of Records relative to the current input file / when using two input files => seperate RecordNumbers
```

### Built-in Functions
```
printf "%10.0f\n" 1.28071e+09               # print scientific notation as float to stdout

var = fprintf("%s %d %.2f\n", "Testing", 1, 3) }' # assigns its output to a variable, not stdout

gsub(/"/, "")                   # remove quotes globally

split($1,swm,".");              # split $1 into array swm[] with optional seperator "."

substr("foobar", 2, 3)          # => "oob"

substr("foobar", 4)             # => "bar"

length("foo")                   # => 3

tolower("FOO")                  # => "foo"

toupper("foo")                  # => "FOO"
```

## see also
- [awk - learnxinyminutes.com](https://learnxinyminutes.com/docs/awk/)
