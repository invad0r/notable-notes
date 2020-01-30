---
tags: [bash]
title: bash array
created: '2019-08-01T07:14:55.242Z'
modified: '2020-01-29T07:18:39.143Z'
---

# bash array

## usage
```sh
array[0] = val               # several ways to define an array
array[1] = val
array[2] = val
array=([2]=val [0]=val [1]=val)
array(val val val)

${array[i]}                  # displays array's value for this index. If no index is supplied, array element 0 is assumed
${#array[i]}                 # length of any element in the array
${#array[@]}                 # how many values there are in the array


declare -A SWARM
SWARM[swarm-a]='swarm-1 swarm-2 swarm-3'
SWARM[swarm-b]='swarm-3 swarm-4 swarm-5'

echo ${SWARM[@]}    # print values
echo ${!SWARM[@]}   # print keys

echo ${SWARM[swarm-1]}
unset SWARM[swarm-1]


declare -a foo=(a b c)
s=1
e=2
foo=("${foo[@]:s:e}")   # remove element
echo ${foo[@]}
b c


function foo() { 
  elem=$1; 
  next=$((elem+1)); 
  shift; 
  declare -a bar=($@); 
  len=${#bar[@]}; 
  [ $elem -ge $len ] && { echo "elem > len"; return 1; }; 
  bar=(${bar[@]:0:elem} ${bar[@]:next}); 
  echo "final: ${bar[@]}"; 
}


Colors=([0]="purple" [1]="reddish-orange" [2]="light green")
echo ${Colors[@]}       # purple reddish-orange light green
declare | grep Colors   # Colors=([0]="purple" [1]="reddish-orange" [2]="light green")
```

## see also
- [[bash declare]]
- [[bash mapfile]]
- [Bash associative array examples – Andy Balaam's Blog](https://www.artificialworlds.net/blog/2012/10/17/bash-associative-array-examples/)
