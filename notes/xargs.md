---
tags: [brew]
title: xargs
created: '2019-07-30T06:19:49.266Z'
modified: '2021-07-01T11:37:55.996Z'
---

# xargs
> command line utility for building an execution pipeline from standard input

## install
`brew install findutils` (as `gxargs`)

## usage

```sh
-I REPL_STR         # Execute utility for each input line, replacing one or more occurrences of replstr in up to replacements (or 5 if no -R flag is specified) arguments to utility with the entire line of input
-R REPLACEMENTS     # Specify the maximum number of arguments that -I will do replacement in.  If replacements is negative, the number of arguments in which to replace is unbounded
-t                  # echo the command to be executed to standard error immediately before it is executed
-p                  # echo each command to be executed and ask the user whether it should be executed
-x                  # force xargs to terminate immediately if a command line containing number arguments will not fit in the specified cli  length
```

```sh
echo 'one two three' | xargs mkdir

echo 'one two three' | xargs -t rm                  # -t prints each command that will be executed

echo 'one two three' | xargs -p touch               # -p will print the command to be executed and prompt the user to run it

cat foo.txt | xargs -I % sh -c 'echo %; mkdir %'    # -I replaces occurrences of the argument with the argument passed to xargs

echo 210    | xargs -I {} bash -c "if [[ "{}" =~ 2 ]]; then echo {}; fi"   # replace string

# when no -I => defaults to `{}`


for file in "$(ls)"; do echo $file" rugal"; done
ls | xargs -I% echo "% rugal"
```

## see also
- [[curl]]
- [[parallel]]
- [Replacement for xargs -d in osx](https://superuser.com/questions/467176/replacement-for-xargs-d-in-osx)
