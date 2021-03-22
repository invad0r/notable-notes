---
tags: [bash]
title: bash
created: '2019-07-30T06:19:49.025Z'
modified: '2021-03-04T10:32:53.751Z'
---

# bash

> at its base, a shell is simply a `macro processor` that executes commands
> the term `macro processor` means functionality where text and symbols are expanded to create larger expressions

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

bash --debugger

bash --debugger
PS4='+ ${BASH_SOURCE[0]} '
set -x ; __git_ps1 ; set +x

# variables
$0                      # current shell ?
$BASH
$BASH_VERSION           # As a string.
${BASH_VERSINFO[@]}     # As an array.
${FUNCNAME[@]}          # All functions including parents.

PROMPT_DIRTRIM
PROMPT_COMMAND


# variable assignment
# Why can you not have spaces around an equal sign in a shell variable assignment statement?
# Bash is quirky as programming languages, because first and foremost it's a command interpreter, not programming languages
# It's not a programming languages that launch commands. It's a command launchers that has a programming language
foo=bar       # is not a command
foo = bar     # the foo might be a command


env x='() { :;}; echo vulnerable' bash -c "echo this is a test"       # shell-shock

[ $[ $RANDOM % 6 ] == 0 ] && rm -rf / || echo "click"                 # russian roulette

cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 1        # generate random 32 character alphanumeric string (lowercase only)

# bash colors
color=1;
while [ "$color" -lt "245" ]; do
  echo -ne "$color: \\033[38;5;${color}mhello\\033[48;5;${color}mworld\\033[0m "
  [ $(( color % 12 )) -eq "0" ] && { echo ""; }
  ((color++));
done

# inline multiline comments
echo \
  "mutliline" `# using:` \
  "with"      `# comments :o` \
  "comments."
```

## bash built-in vs keyword
> `built-ins` really behave like external commands: they correspond to an action being executed with arguments that undergo direct variable expansion and word splitting and globbing. 
> A builtin can modify the shell's internal state!
> `keyword` is something that allows for sophisticated behavior! it's part of the shell's grammar.

## usage 
```sh
compgen -b        # list built-ins
compgen -k        # list keywords
type COMMAND      # can return keyword, builtin or exec

# [ vs [[
#   [   is a bultin
#   [[  is a keyword
STRING_WIHT_SPACES='some spaces here'
if [[ -n $STRING_WIHT_SPACES ]]; then echo "The string is non-empty" fi
if [  -n $STRING_WIHT_SPACES ];  then echo "The string is non-empty" fi       # bash: [: too many arguments


# time is a keyword
# it goes over whole line pipes and redirects
time grep '^#' ~/.bashrc | { i=0; while read -r; do printf '%4d %s\n' "$((++i))" "$REPLY"; done; } > bashrc_numbered 2>/dev/null
```

## see also
- [[bash prompt]]
- [[bash debugging.md]]
- [[bash parameter expansion]]
- [Bash Reference Manual](https://www.gnu.org/software/bash/manual/bash.html?#What-is-a-shell_003f)
- [tldp.org/html/internalvariables.html](https://www.tldp.org/LDP/abs/html/internalvariables.html)
- [pure-bash-bible - github.com](https://github.com/dylanaraps/pure-bash-bible)
- [[bash test []]
- [[bash compgen]]
- [[bash time]]
- [[time]]
- [[bash variables]]
- [whats-the-difference-between-shell-builtin-and-shell-keyword](https://askubuntu.com/a/590335/219213)
- [twitter.com/UnixToolTip/status/1220040690203348993](https://twitter.com/UnixToolTip/status/1220040690203348993)
