---
tags: [bash]
title: bash history expansion
created: '2019-07-30T06:19:49.010Z'
modified: '2019-08-18T19:59:23.562Z'
---

# bash history expansion

[[bash history]]

## `bang bang`
```sh
!!		          # repeats the last command
sudo !!

!-2             # relative to current index

!14934		      # executes command in history with number 14934

!m		          # executes command in history starting with "m.."


!ech		        # e.g. autocompletes last command starting with ech maybe echo something
```

### modifieres
> After the optional word designator, you can add a sequence of one or more of the following modifiers, each preceded by a `:` 
```sh

h             # Remove a trailing pathname component, leaving only the head.
t             # Remove all leading pathname components, leaving the tail.
r             # Remove a trailing suffix of the form ‘.suffix’, leaving the basename.
e             # Remove all but the trailing suffix.

p             # Print the new command but do not execute it.
!ech:p	      # :p prints command

q             # Quote the substituted words, escaping further substitutions.
x             # Quote the substituted words as with ‘q’, but break into words at spaces, tabs, and newlines.
s/old/new/    # Substitute new for the first occurrence of old in the event line. Any delimiter may be used in place of ‘/’. The delimiter may be quoted in old and new with a single backslash. If ‘&’ appears in new, it is replaced by old. A single backslash will quote the ‘&’. The final delimiter is optional if it is the last character on the input line.
&    # Repeat the previous substitution.
g
a    # Cause changes to be applied over the entire event line. Used in conjunction with ‘s’, as in gs/old/new/, or with ‘&’.
G    # Apply the following ‘s’ modifier once to each word in the event.

```
[Bash Reference Manual - Modifiers](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Modifiers)


### Expanding for historical arguments

```sh
ls !^           # get the first argument of a particular command

!$		          # get the last argument

!1-$:p          #


!*              # get all arguments (but not the command itself)
```

```sh
!                    # Start a history substitution, except when followed by a space, tab, the end of the line, 
                     # ‘=’ or ‘(’ (when the extglob shell option is enabled using the shopt builtin).
!n                   # Refer to command line n.
!-n                  # Refer to the command n lines back.
!!                   # Refer to the previous command. This is a synonym for ‘!-1’.
!string              # Refer to the most recent command preceding the current position in the history list starting with string.

!?string[?]          # Refer to the most recent command preceding the current position in the history list containing string. 
                     # The trailing ‘?’ may be omitted if the string is followed immediately by a newline.

^string1^string2^    # Quick Substitution. Repeat the last command, replacing string1 with string2.                    
# Equivalent to 
!!:s/string1/string2/.

!#                   # The entire command line typed so far.

```

[Bash Event-Designators](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Event-Designators)
