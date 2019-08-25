---
tags: [bash/builtin]
title: bash read
created: '2019-07-30T06:19:49.017Z'
modified: '2019-08-20T07:21:21.972Z'
---

# bash read



## password input
```sh
local PASSWORD
read -s -p "Password:" PASSWORD

  # -s      do not echo input coming from a terminal
  # -p      prompt output the string PROMPT without a trailing newline before attempting to read
```

### READ variable
```sh
while read; do echo "$REPLY"; done

echo "Hello, world!" | (read; echo "$REPLY")
```
> the entire line of text is stored in the variable REPLY


```sh
echo "one two three four" | while read -a wordarray; do
  echo ${wordarray[1]}
done
```

### ifs
```sh
IFS=','; while read; do echo "reply:" $REPLY; done < <(echo "1,2,3,4")

while IFS=','; read; do echo "reply:" $REPLY; done < <(echo "1,2,3,4")


# find is not affected by IFS, because after while and therefore inside loop
while IFS= read -r -d $'\0' file; do
  echo "$file"
done < <(find . -print0)
```
[Bash read builtin command help and examples](https://www.computerhope.com/unix/bash/read.htm)
