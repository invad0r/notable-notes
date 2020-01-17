---
tags: [bash]
title: bash ifs
created: '2019-07-30T06:19:49.012Z'
modified: '2020-01-16T20:29:59.463Z'
---

# bash ifs

> `internal field seperator`




occurs once any of the following expansions are done (and only then!)
- `Parameter expansion`: `${}`
- `Command substitution`: `$()`
- `Arithmetic expansion`: `$(())`

Bash will scan the results of these expansions for special `IFS` characters that mark word boundaries. This is only done on results that are not double-quoted!

The IFS variable holds the characters that Bash sees as word boundaries in this step. The default contains the characters
- `<space>`
- `<tab>`
- `<newline>`

## usage
```sh
IFS=          # sets the internal field separator to "no value".
              # <space>, <tab>, and <newline> are therefore considered part of a word, 
              # which will preserve white space in the file names.

IFS=$'\t'     # sets tab as field seperator

IFS=$'\n'     # sets linebreak as field seperator



mystring="foo:bar baz rab"

IFS=
for word in $mystring; do
    echo "Word: $word"
done
```

## see also
- [WordSplitting - Greg's Wiki](http://mywiki.wooledge.org/WordSplitting)
- [Word splitting [Bash Hackers Wiki]](http://wiki.bash-hackers.org/syntax/expansion/wordsplit)
