---
tags: [bash]
title: bash array
created: '2019-08-01T07:14:55.242Z'
modified: '2019-08-25T20:05:14.674Z'
---

# bash array

```sh
array[0] = val               # several ways to define an array
array[1] = val
array[2] = val
array=([2]=val [0]=val [1]=val)
array(val val val)

${array[i]}                  # displays array's value for this index. If no index is supplied, array element 0 is assumed
${#array[i]}                 # to find out the length of any element in the array
${#array[@]}                 # to find out how many values there are in the array


declare -A SWARM
SWARM[swarm-a]='swarm-1 swarm-2 swarm-3'
SWARM[swarm-b]='swarm-3 swarm-4 swarm-5'

echo ${SWARM[@]}    # print values
echo ${!SWARM[@]}   # print keys

echo ${SWARM[swarm-1]}
unset SWARM[sswarm-1]
```

## see also
- [[bash declare]]
- [Bash associative array examples – Andy Balaam's Blog](https://www.artificialworlds.net/blog/2012/10/17/bash-associative-array-examples/)
