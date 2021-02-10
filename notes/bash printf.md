---
tags: [bash/built-in]
title: bash printf
created: '2019-07-30T06:19:49.208Z'
modified: '2021-02-04T13:06:41.726Z'
---

# bash printf

> formats and prints ARGUMENTS under control of the FORMAT

## usage
```sh
printf [-v var] format [arguments]

#  -v var    assign the output to shell variable VAR rather than display it on the standard output
#   addional formats:
#     %b        expand backslash escape sequences in the corresponding argument
#     %q        quote the argument in a way that can be reused as shell input
#     %(fmt)T   output the date-time string resulting from using FMT as a format string for strftime(3)


printf '%x\n' 12        # print hex: C

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
```

## see also
- [[watch]]
- [[bash arithmetic expansion]]
- [[bc]]
- [[echo]]
