---
tags: [shell/bash]
title: bash getopts
created: '2019-07-30T06:19:49.009Z'
modified: '2021-05-12T08:46:51.095Z'
---

# bash getopts

> parse positional parameters as options

## usage
```sh
# variables
OPTIND      # option-index; initialized to 1
OPTARG      # getopts places argument to OPTARG when option requires argument
OPTSTRING   # contains option letters to be recognized; 
            # if a letter is followed by a colon, the option is expected to have an argument, which should be separated from it by white space
OPTERR      # default: 1, if set 0, getopts disables the printing of error messages


while getopts u:d:p:f: option; do
  case "${option}" in
    u) USER=${OPTARG}     ;;
    d) DATE=${OPTARG}     ;;
    p) PRODUCT=${OPTARG}  ;;
    f) FORMAT=$OPTARG     ;;
  esac
done
```

## see also
- [[bash while]]
- [[bash case]]
- [[bash arguments]]
