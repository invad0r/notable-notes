---
tags: [shell/bash]
title: bash parameter expansion
created: '2019-07-30T06:19:49.015Z'
modified: '2021-11-08T16:04:06.116Z'
---

# bash parameter expansion 

> `${parameter}` the value of parameter is substituted

## positional parameter

```sh
${0}      # ($0) expands to the name of the shell or shell script. This is set at shell initialization. 
          # If Bash is invoked with a file of commands (see Shell Scripts), $0 is set to the name of that file. 
          # If Bash is started with the -c option (see Invoking Bash), then $0 is set to the first argument after the string to be executed, if one is present. 
          # Otherwise, it is set to the filename used to invoke Bash, as given by argument zero.
${1}
```

## special parameter

```sh
${@}      # expands positional params to seperate words: `$1`, `$2`, ..`$N`
${*}      # expands positional params to one words: `$1c$2c..` `c` is the first character of `IFS`

${*}      # expands to the positional parameters, starting from one. When the expansion is not within double quotes, each positional parameter expands to a separate word. In contexts where it is performed, those words are subject to further word splitting and pathname expansion. When the expansion occurs within double quotes, it expands to a single word with the value of each parameter separated by the first character of the IFS special variable. That is, "$*" is equivalent to "$1c$2c…", where c is the first character of the value of the IFS variable. If IFS is unset, the parameters are separated by spaces. If IFS is null, the parameters are joined without intervening separators.

${@}      # expands to the positional parameters, starting from one. In contexts where word splitting is performed, this expands each positional parameter to a separate word; if not within double quotes, these words are subject to word splitting. In contexts where word splitting is not performed, this expands to a single word with each positional parameter separated by a space. When the expansion occurs within double quotes, and word splitting is performed, each parameter expands to a separate word. That is, "$@" is equivalent to "$1" "$2" …. If the double-quoted expansion occurs within a word, the expansion of the first parameter is joined with the beginning part of the original word, and the expansion of the last parameter is joined with the last part of the original word. When there are no positional parameters, "$@" and $@ expand to nothing (i.e., they are removed).

${#}      # `$#` expands to the number of positional parameters in decimal.

${?}      # `$?` expands to the exit status of the most recently executed foreground pipeline.

${-}      # `$-` expands to the current option flags as specified upon invocation, by the set builtin command, or those set by the shell itself (such as the -i option).


${$}      # `$$` expands to the process ID of the shell. In subshell, it expands to the process ID of the invoking shell, not the subshell

${!}      # `$!` expands to the process ID of the job most recently placed into the background, whether executed as an asynchronous command or using the bg builtin (see Job Control Builtins).


${_}      # `$_` At shell startup, set to the absolute pathname used to invoke the shell or shell script being executed 
          # set to final argument of previous command executed.
```

## indirect expansion

```sh
NAME="VARIABLE"
VARIABLE=42
echo ${!NAME}   # 42

# exceptions to this are the expansions of:
${!prefix*} 
${!name[@]}
```

## substring

```sh
${PARAMETER#PATTERN}      # match from beginning/left to end/right
#        --->
${PARAMETER##PATTERN}     # more greedy


${PARAMETER%PATTERN}      # match from end/right to beginning/left
#        <---   
${PARAMETER%%PATTERN}     # more greendy

${pages%%[[:cntrl:]]}     # remove carriage-return symbol \r


for i in $(ls -d docker-*); do mv $i ${i#docker-}; done         # remove prefix "docker-" from directories

[ ! -z "${NUM##*[!0-9]*}" ] && { echo "is a number: $NUM"; }    # check if number
```

## substring expansion

```sh
${string:offset}           # Extracts substring from $string at $offset
                           # If the $string parameter is "*" or "@", then this extracts the positional parameters, 
                           # [1] starting at $offset.

${string:offset:length}  # extracts $length characters of substring from $string at $offset.


FOO="9781786466204-go_design_patterns.pdf"
echo ${FOO:0:13};  # 9781786466204
echo ${FOO:14};    # go_design_patterns.pdf
```

## string replacement

```sh
${var/Pattern/Replacement}      # First match of Pattern, within var replaced with Replacement
${var//Pattern/Replacement}     # All matches of Pattern, within var replaced with Replacement

# e.g. url decoding:
: "${*//+/ }";
echo -e "${_//%/\\x}"
```

##  modifie alphabetic characters

- if pattern is omitted, it is treated like a `?`, which matches every character. 
- if parameter is `@` or `*`, the case modification operation is applied to each positional parameter in turn, and the expansion is the resultant list
- if parameter is an array variable subscripted with `@` or `*`, the case modification operation is applied to each member of the array in turn, and the expansion is the resultant list.

```sh
${parameter^pattern}
${parameter^^pattern}

${parameter,pattern}
${parameter,,pattern}

echo ${FOO^^}   # all upercase

echo ${foo,,}   # all to lowercase
echo ${foo^^}   # all to upercase
```

## pattern matching

```sh
*         # matches any string including null string
?         # matches any single character
[...]     # machtes any one of enclosed characters, character-ranges and character classes
          # [a-z], [A-E] character ranges
          # if the first character is a `!` or `^` then any character not enclosed is matched
[:class:] # [:word:]  matches letters, digits, and the character `_`
          # [:alnum:] [:alpha:] [:ascii:] [:blank:] [:cntrl:] [:digit:] [:graph:] 
          # [:lower:] [print:] [:punct:] [:space:] [:upper:] [:xdigit:]

## extended pattern list
# if the `extglob` shell option is enabled (`shopt -s extglob`)
# a `pattern-list` is a list of one or more patterns separated by a `|`
?(pattern-list)     # Matches zero or one occurrence of the given patterns
*(pattern-list)     # Matches zero or more occurrences of the given patterns
+(pattern-list)     # Matches one or more occurrences of the given patterns
@(pattern-list)     # Matches one of the given patterns
!(pattern-list)     # Matches anything except one of the given patterns
```

## see also

- [[tr]]
- [[bash]]
- [[bash braces]]
- [[bash globbing]]
- [[bash set unset]]
- [[bash source vs execute]]
- [gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Shell-Parameter-Expansion](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Shell-Parameter-Expansion)
- [gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Shell-Parameters](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Shell-Parameters)
- [gnu.org/software/bash/manual/html_node/Pattern-Matching](https://www.gnu.org/software/bash/manual/html_node/Pattern-Matching.html)
- [Remove \\r from echoing out in bash script - Super User](https://superuser.com/a/1215968)
