---
tags: [bash]
title: bash parameter expansion
created: '2019-07-30T06:19:49.015Z'
modified: '2019-07-30T06:22:29.796Z'
---

# bash parameter expansion 


```sh
$@     # expands positional params to seperate words: `$1` `$2`..`$N`
$*     # expands positional params to one words: `$1c$2c..` `c` is the first character of `IFS`
```

## substring

```sh
${PARAMETER#PATTERN}      # match from beginning/left to end/right

${PARAMETER##PATTERN}     # more greedy

${PARAMETER%PATTERN}      # match from end/right to beginning/left

${PARAMETER%%PATTERN}     # more greendy



${string:position}         # Extracts substring from $string at $position.
                           # If the $string parameter is "*" or "@", then this extracts the positional parameters, 
                           # [1] starting at $position.

${string:position:length}  # Extracts $length characters of substring from $string at $position.


FOO="9781786466204-go_design_patterns.pdf"

echo ${FOO:0:13};  # 9781786466204
echo ${FOO:14};    # go_design_patterns.pdf
```

```sh
for i in $(ls -d docker-*); do mv $i ${i#docker-}; done         # remove prefix "docker-" from directories

[ ! -z "${NUM##*[!0-9]*}" ] && { echo "is a number: $NUM"; }    # check if number
```


