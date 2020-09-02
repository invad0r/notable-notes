---
tags: [bash]
title: bash
created: '2019-07-30T06:19:49.025Z'
modified: '2020-08-11T07:08:47.094Z'
---

# bash

> At its base, a shell is simply a `macro processor` that executes commands. The term `macro processor` means functionality where text and symbols are expanded to create larger expressions. 

## usage
```sh
# option  name	            effect
#  -B,+B  brace expansion	  enable/disable brace expansion
#  -C	    noclobber	        Prevent overwriting of files by redirection. overridden by `>|`
#  -D	          	          List double-quoted strings prefixed by $, but do not execute commands in script
#  -a	    allexport	        Export all defined variables
#  -b	    notify	          Notify when jobs running in background terminate (not of much use in a script)
#  -c ..	      	          Read commands from `..`
#
#  checkjobs: Informs user of any open jobs upon shell exit
#  -e	    errexit	          abort script at first error, when a command exits with non-zero status 
#                           (except in `until` or `while` loops, if-tests, list constructs)
#  -f	    noglob	          filename expansion (globbing) disabled
#
#  globstar:	globbing star-match	Enables the ** globbing operator. Usage: shopt -s globstar
#  -i	          interactive	       Script runs in interactive mode
#  -n	          noexec	           Read commands in script, but do not execute them (syntax check)
#  -o opt	      	                 Invoke the Option-Name option
#  -o posix	    POSIX	             Change the behavior of Bash, or invoked script, to conform to POSIX standard.
#  -o pipefail	pipefailure	       Causes a pipeline to return the exit status of the last command in the pipe that returned a non-zero return value.
#  -p	          privileged	        Script runs as "suid" (caution!)
#  -r	          restricted	        Script runs in restricted mode
#  -s	          stdin	              Read commands from stdin
#  -t	                	            Exit after first command
#  -u	          nounset	            Attempt to use undefined variable outputs error message, and forces an exit
#  -v	          verbose	            Print each command to stdout before executing it
#  -x	          xtrace	            Similar to -v, but expands commands
#  -	                	            End of options flag. All other arguments are positional parameters.
#  --	                	            Unset positional parameters. If arguments given (-- arg1 arg2), positional parameters set to arguments.

bash -c "echo 1"    # read command-string

# variables
$0                      # current shell ?
$BASH
$BASH_VERSION           # As a string.
${BASH_VERSINFO[@]}     # As an array.
${FUNCNAME[@]}          # All functions including parents.

env x='() { :;}; echo vulnerable' bash -c "echo this is a test"       # shell-shock

[ $[ $RANDOM % 6 ] == 0 ] && rm -rf / || echo "click"                 # russian roulette


# generate random 32 character alphanumeric string (lowercase only)
cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 1          

# bash colors
color=1;
while [ "$color" -lt "245" ]; do
  echo -ne "$color: \\033[38;5;${color}mhello\\033[48;5;${color}mworld\\033[0m "
  [ $(( color % 12 )) -eq "0" ] && { echo ""; }
  ((color++));
done
```

## see also
- [[bash prompt]]
- [[bash debugging.md]]
- [[bash parameter expansion]]
- [[bash built-in vs keyword]]
- [Bash Reference Manual](https://www.gnu.org/software/bash/manual/bash.html?#What-is-a-shell_003f)
- [tldp.org/html/internalvariables.html](https://www.tldp.org/LDP/abs/html/internalvariables.html)
- [pure-bash-bible - github.com](https://github.com/dylanaraps/pure-bash-bible)
