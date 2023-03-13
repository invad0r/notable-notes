---
tags: [shell/bash/builtin]
title: bash mapfile
created: '2019-07-30T06:19:49.014Z'
modified: '2022-04-27T14:29:48.400Z'
---

# bash mapfile

> read lines from stdin into an indexed array variable

## flag

```sh
-c QUANTUM 	        # Specifies the number of lines that have to be read between every call to the callback specified with -C - default QUANTUM is 5000
-C CALLBACK 	      # Specifies a callback, which can be any shell code, the index of the array that will be assigned, and the line is appended at evaluation time
-n COUNT 	          # Reads at most COUNT lines, then terminates. If COUNT is 0, then all lines are read (default)
-O ORIGIN 	        # Starts populating the given array ARRAY at the index ORIGIN rather than clearing it and starting at index 0
-s COUNT 	          # Discards the first COUNT lines read
-t 	                # Remove any trailing newline from a line read, before it is assigned to an array element
-u FD 	            # Read from filedescriptor FD rather than standard input
```

## usage

```sh
readarray

mapfile

mapfile -t < <(printf "Line 1\nLine 2\nLine 3")
printf "%s\n" "${MAPFILE[@]}"


mapfile FOORRAY < <(CMD | awk '{ if( $1 ~ "swarm" && $3 == "alive") { split($2, arr, ":");  print $1, arr[1]} }')
echo ${FOORAY[@]}
```

## see also

- [wiki-dev.bash-hackers.org/commands/builtin/mapfile](https://wiki-dev.bash-hackers.org/commands/builtin/mapfile)
- [[bash read]]
- [[bash array]]
- [[bash readarray]]
- [[yq]]
