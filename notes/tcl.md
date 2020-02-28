---
title: tcl
created: '2020-02-25T07:16:45.951Z'
modified: '2020-02-26T08:02:40.410Z'
---

# tcl

> `tcl` - `Tool Command Language`, is an open-source multi-purpose c library which includes a powerful dynamic scripting language

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
- https://wiki.tcl-lang.org/page/What+is+Tcl
