---
tags: [dsl]
title: tcl
created: '2020-02-25T07:16:45.951Z'
modified: '2020-09-02T18:15:00.598Z'
---

# tcl

> `tcl` - `Tool Command Language` - multi-purpose `c` library which includes a powerful dynamic scripting language
> pronounced "tickle" or "tee cee ell"
> high-level, general-purpose, interpreted, dynamic programming language

## install
`brew cask install tcl`

## usage
```sh
tclsh    # start tcl shell
```
```tcl
puts $tcl_version     # prints tcl version

puts [ls -l]          # square-bracket used for command substitution
```
```tcl
#!/usr/bin/tclsh

set variableA 10
set {variable B} test
puts $variableA
puts ${variable B}
```

## see also
- [wiki.tcl-lang.org/page/What+is+Tcl](https://wiki.tcl-lang.org/page/What+is+Tcl)
- [[lua]]
