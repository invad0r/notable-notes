---
tags: [shell/bash/builtin]
title: bash readarray
created: '2019-08-02T06:42:37.622Z'
modified: '2022-05-03T07:44:31.166Z'
---

# bash readarray

> synonym for [[bash mapfile]] - read lines from a FILE into an array variable

## option

```sh
-d DELIM            # delimiter to terminate lines, instead of newline
-n COUNT            # Copy at most COUNT lines.  If COUNT is 0, all lines are copied
-O ORIGIN           # Begin assigning to ARRAY at index ORIGIN.  The default index is 0
-s COUNT            # Discard first COUNT lines read
-t                  # remove trailing DELIM from each line read (default newline)
-u FD               # Read lines from file descriptor FD instead of the stdin
-C CALLBACK         # Evaluate CALLBACK each time QUANTUM lines are read
-c quantum          # Specify the number of lines read between each call to CALLBACK
```

## usage

```sh
readarray ARRAY < <(yq e '.coolActions[]' sample.yaml)
 echo "${ARRAY[1]}"

string='Paris, France, Europe';
readarray -td, ARRAY <<<"$string"; 
declare -p ARRAY;
# declare -a ARRAY=([0]="Paris" [1]=" France" [2]=$' Europe\n')

readarray -td: ARRAY <<<$STRING    # split here-string into array STRING="8:30"
```

## see also

- [[bash read]]
- [[bash array]]
- [[bash declare]]
- [[bash redirects]]
- [[yq]]
- [[jq]]
