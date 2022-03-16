---
tags: [shell/bash/builtin]
title: bash read
created: '2019-07-30T06:19:49.017Z'
modified: '2022-03-11T08:37:58.622Z'
---

# bash read

> Read a line from the stdin and split it into fields

## environment variables

```sh
REPLY       #
```

## flags

```sh
-a          # save to array
-n          # defines the required character count to stop reading
-s          # hides the user's input
-r          # causes the string to be interpreted "raw" (without considering backslash escapes)
-s          # do not echo input coming from a terminal
-p          # prompt output the string PROMPT without a trailing newline before attempting to read
```

## usage

```sh
echo 1 2 | { read a b; echo $a $b; }

read a b < <(echo 1 2);  echo $a $b;            # save to multiple vairables

read -a foo < <(echo 1 2);                      # save to array


read input </dev/tty                            # read inside read loop

read -p "Press enter to continue"               # needs return-key !
read -n 1 -s -r -p "Press any key to continue"  # any key


read -s -p "Password:" PASSWORD                 # password input


# the entire line of text is stored in the variable REPLY
while read; do echo "$REPLY"; done
  echo "Hello, world!" | (read; echo "$REPLY")
done

echo "one two three four" | while read -a wordarray; do
  echo ${wordarray[1]}
done


IFS=','; while read; do echo "reply:" $REPLY; done < <(echo "1,2,3,4")

while IFS=','; read; do echo "reply:" $REPLY; done < <(echo "1,2,3,4")


# find is not affected by IFS, because after while and therefore inside loop
while IFS= read -r -d $'\0' file; do
  echo "$file"
done < <(find . -print0)
```

## see also

- [[bash redirects]]
- [[bash exec]]
- [[bash mapfile]] [[bash readarray]]
- [[bash while]]
- [[bash process substitution]]
- [computerhope.com/unix/bash/read](https://www.computerhope.com/unix/bash/read.htm)
- [why-piping-input-to-read-only-works-when-fed-into-while-read-construct](https://stackoverflow.com/questions/13763942/why-piping-input-to-read-only-works-when-fed-into-while-read-construct)
- [stackoverflow.com/read-input-in-bash-inside-a-while-loop](https://stackoverflow.com/questions/6883363/read-input-in-bash-inside-a-while-loop)
- [compgroups.net/comp.unix.shell/fixing-stdin-inside-a-redirected-loop](http://compgroups.net/comp.unix.shell/fixing-stdin-inside-a-redirected-loop/400460)

