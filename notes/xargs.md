---
tags: [brew]
title: xargs
created: '2019-07-30T06:19:49.266Z'
modified: '2020-02-19T10:22:52.688Z'
---

# xargs
> command line utility for building an execution pipeline from standard input

## install
`brew install findutils` (as `gxargs`)

## usage
```sh
echo 'one two three' | xargs mkdir

echo 'one two three' | xargs -t rm                  # -t prints each command that will be executed 

echo 'one two three' | xargs -p touch               # -p will print the command to be executed and prompt the user to run it

cat foo.txt | xargs -I % sh -c 'echo %; mkdir %'    # -I replaces occurrences of the argument with the argument passed to xargs

echo 210    | xargs -I {} bash -c "if [[ "{}" =~ 2 ]]; then echo {}; fi"   # replace string

# when no -I => defaults to `{}`
```

## see also
- [[curl]]
- [[parallel]]
- [Replacement for xargs -d in osx](https://superuser.com/questions/467176/replacement-for-xargs-d-in-osx)
