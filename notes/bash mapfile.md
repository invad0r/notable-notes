---
tags: [bash/built-in]
title: bash mapfile
created: '2019-07-30T06:19:49.014Z'
modified: '2020-01-10T10:17:09.580Z'
---

# bash mapfile

>

## usage
```sh
mapfile    [-n COUNT] [-O ORIGIN] [-s COUNT] [-t] [-u FD] [-C CALLBACK] [-c QUANTUM] [ARRAY]

readarray  [-n COUNT] [-O ORIGIN] [-s COUNT] [-t] [-u FD] [-C CALLBACK] [-c QUANTUM] [ARRAY]


mapfile -t < <(printf "Line 1\nLine 2\nLine 3")
printf "%s\n" "${MAPFILE[@]}"


mapfile FOORRAY < <(consul-node dev | awk '{ if( $1 ~ "swarm" && $3 == "alive") { split($2, arr, ":");  print $1, arr[1]} }')
echo ${FOORAY[@]}
```

## see also
- [[bash array]]
