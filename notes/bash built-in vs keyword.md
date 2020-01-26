---
favorited: true
tags: [bash]
title: bash built-in vs keyword
created: '2019-08-02T08:47:35.961Z'
modified: '2020-01-23T09:09:03.460Z'
---

# bash built-in vs keyword

> `built-ins` really behave like external commands: they correspond to an action being executed with arguments that undergo direct variable expansion and word splitting and globbing. A builtin can modify the shell's internal state!
> `keyword` is something that allows for sophisticated behavior! it's part of the shell's grammar.

## list 
```sh
compgen -b    # list built-ins
compgen -k    # list keywords
```

## `[[` vs `[`
```sh
string_with_spaces='some spaces here'
if [[ -n $string_with_spaces ]]; then echo "The string is non-empty" fi


string_with_spaces='some spaces here'
if [ -n $string_with_spaces ]; then echo "The string is non-empty" fi
# bash: [: too many arguments
```

## time goes over whole line pipes and redirects
```sh
time grep '^#' ~/.bashrc | { i=0; while read -r; do printf '%4d %s\n' "$((++i))" "$REPLY"; done; } > bashrc_numbered 2>/dev/null
```

## variable assignment
> Why can you not have spaces around an equal sign in a shell variable assignment statement? 
```sh
foo=bar       # is not a command
foo = bar     # the foo might be a command.
```
> Bash is quirky as programming languages, because first and foremost it's a command interpreter, not programming languages
> It's not a programming languages that launch commands. It's a command launchers that has a programming language


## see also
- [[bash test []]
- [[bash compgen.md]]
- [[bash time]]
- [whats-the-difference-between-shell-builtin-and-shell-keyword](https://askubuntu.com/a/590335/219213)
- [[bash variables]]
- https://twitter.com/UnixToolTip/status/1220040690203348993?s=20

