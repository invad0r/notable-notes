---
tags: [bash/built-in]
title: bash read
created: '2019-07-30T06:19:49.017Z'
modified: '2020-03-16T17:06:53.106Z'
---

# bash read

> Read a line from the stdin and split it into fields

## usage
```sh
echo 1 2 | { read a b; echo $a $b; }

read a b < <(echo 1 2);  echo $a $b;            # save to multiple vairables

read -a foo < <(echo 1 2);                      # save to array


read input </dev/tty                            # read inside read loop

read -p "Press enter to continue"               # needs return-key !
read -n 1 -s -r -p "Press any key to continue"  # any key
  # -n      defines the required character count to stop reading
  # -s      hides the user's input
  # -r      causes the string to be interpreted "raw" (without considering backslash escapes)


# password input
local PASSWORD
read -s -p "Password:" PASSWORD
  # -s      do not echo input coming from a terminal
  # -p      prompt output the string PROMPT without a trailing newline before attempting to read


# `$REPLY` the entire line of text is stored in the variable REPLY
while read; do echo "$REPLY"; done
  echo "Hello, world!" | (read; echo "$REPLY")
done


echo "one two three four" | while read -a wordarray; do
  echo ${wordarray[1]}
done


# `ifs`
IFS=','; while read; do echo "reply:" $REPLY; done < <(echo "1,2,3,4")

while IFS=','; read; do echo "reply:" $REPLY; done < <(echo "1,2,3,4")


# find is not affected by IFS, because after while and therefore inside loop
while IFS= read -r -d $'\0' file; do
  echo "$file"
done < <(find . -print0)
```

## see also
- [[bash mapfile]]
- [[bash while]]
- [[bash process substitution]]
- [Bash read builtin command help and examples](https://www.computerhope.com/unix/bash/read.htm)
- [why-piping-input-to-read-only-works-when-fed-into-while-read-construct](https://stackoverflow.com/questions/13763942/why-piping-input-to-read-only-works-when-fed-into-while-read-construct)
- https://stackoverflow.com/questions/6883363/read-input-in-bash-inside-a-while-loop
- http://compgroups.net/comp.unix.shell/fixing-stdin-inside-a-redirected-loop/400460
