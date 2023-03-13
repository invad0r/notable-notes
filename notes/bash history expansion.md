---
tags: [shell/bash]
title: bash history expansion
created: '2019-07-30T06:19:49.010Z'
modified: '2022-04-27T14:27:39.423Z'
---

# bash history expansion

> introduce words from the history list into the input stream, making it easy to repeat commands, insert the arguments to a previous command into the current input line, or fix errors in previous commands quickly

## usage

```sh
!               # Start a history substitution, except when followed by a space, tab, the end of the line, 
                # ‘=’ or ‘(’ (when the extglob shell option is enabled using the shopt builtin).

!!              # `bang bang`: Refer to the previous command. This is a synonym for ‘!-1’
!!		          # repeats the last command
sudo !!

!n              # Refer to command line n.
!14934		      # executes command in history with number 14934

!-n             # Refer to the command n lines back.
!-2             # relative to current index

!1-$:p

!string         # Refer to the most recent command preceding the current position in the history list starting with string.
!m		          # executes command in history starting with "m.."
!ech		        # e.g. autocompletes last command starting with ech maybe echo something
!ech:p	        # :p prints command

!^                  # get the first argument of a particular command
ls ls !^

!$		              # get the last argument
mkdir foo && cd !$

!*                    # get all arguments, but not the command itself

!#                    # entire command line typed so far

!?string[?]           # Refer to the most recent command preceding the current position in the history list containing string. 
                      # trailing `?` may be omitted if the string is followed immediately by a newline

^string1^string2^       # quick substitution - repeat the last command, replacing string1 with string2
# Equivalent to 
!!:s/string1/string2/.
```

## modifieres

after optional word designator, you can add a sequence of one or more of the following modifiers, each preceded by `:`

```sh
h       # remove a trailing pathname component, leaving only the head
t       # remove all leading pathname components, leaving the tail
r       # remove a trailing suffix of the form ‘.suffix’, leaving the basename
e       # remove all but the trailing suffix
p       # print the new command but do not execute it.
q       # quote the substituted words, escaping further substitutions.
x       # quote the substituted words as with ‘q’, but break into words at spaces, tabs, and newlines

s/old/new/    # Substitute new for the first occurrence of old in the event line. Any delimiter may be used in place of `/`
#                 delimiter may be quoted in old and new with a single backslash. 
#                 If ‘&’ appears in new, it is replaced by old. 
#                 A single backslash will quote the ‘&’. The final delimiter is optional if it is the last character on the input line.
#         &    repeat the previous substitution
#         g
#         a    cause changes to be applied over the entire event line. Used in conjunction with ‘s’, as in gs/old/new/, or with ‘&’
#         G    apply the following ‘s’ modifier once to each word in the event
```

## see also

- [[bash history]]
- [Bash Event-Designators](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Event-Designators)
- [Bash Reference Manual - Modifiers](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Modifiers)
