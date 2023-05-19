---
tags: [shell/bash/builtin]
title: bash printf
created: '2019-07-30T06:19:49.208Z'
modified: '2023-05-19T10:38:37.969Z'
---

# bash printf

> formats and prints ARGUMENTS under control of the FORMAT

## option

```sh
-v VAR   # assign the output to shell variable VAR rather than display it on the standard output
```

## format

```sh
%b        # expand backslash escape sequences in the corresponding argument
%q        # quote the argument in a way that can be reused as shell input
%(fmt)T   # output the date-time string resulting from using FMT as a format string for strftime(3)
```

## usage

```sh
printf '%x\n' 12        # print hex: C

printf '\112\n' # octal
printf '\x4a\n' # hex

printf "\\$(printf %o 74)\n" # octal
printf "\\$(printf %o 74)\n" # octal

printf "time: %s sec\n" $(expr $end - $start)

echo "$(printf '*%.s' {1..40})"     # draw line seperator

printf "%q" "${pages}" 

printf "%q\n" *         # show non visible characters in file name e.g.


printf "\33c"           # clear screen
printf "\033c";

# arithmetic float
printf "%.3f\n" $((1+1/2))                      # 1.000
printf "%.3f\n" $( echo "1+1/2" | bc -l )       # 1.500

# progress spinner
i=1; sp="/-\|"; echo -n ' '; while :; do printf "\b${sp:i++%${#sp}:1}"; done

for ((i=32;i<127;i++)) do printf "\\$(printf %03o "$i")"; done printf "\n"    # print all avail. characters
```

## see also

- [[stat]]
- [[watch]]
- [[bc]]
- [[echo]]
- [[od]]
- [[seq]]
- [[ascii]]
- [[bash arithmetic expansion]]
