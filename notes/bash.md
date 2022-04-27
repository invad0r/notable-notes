---
tags: [shell/bash]
title: bash
created: '2019-07-30T06:19:49.025Z'
modified: '2022-04-06T11:37:34.390Z'
---

# bash

> at its base, a shell is simply a `macro processor` that executes commands
> the term `macro processor` means functionality where text and symbols are expanded to create larger expressions

[gnu.org/what-is-a-shell](https://www.gnu.org/software/bash/manual/html_node/What-is-a-shell_003f.html)

## flags

```sh
# option    name	                effect
-B,+B       brace expansion	    # enable/disable brace expansion
-C	        noclobber	          # prevent overwriting of files by redirection. overridden by `>|`
-D	          	                # List double-quoted strings prefixed by $, but do not execute commands in script
-a	        allexport	          # export all defined variables
-b	        notify	            # Notify when jobs running in background terminate (not of much use in a script)
-c ..	      	                  # Read commands from `..`

#  checkjobs: Informs user of any open jobs upon shell exit
-e	    errexit	                # abort script at first error, when a command exits with non-zero status; except in `until` or `while` loops, if-tests, list constructs
-f	    noglob	                # filename expansion (globbing) disabled

#  globstar:	globbing star-match	Enables the ** globbing operator. Usage: shopt -s globstar
-i	          interactive	      # runs script in interactive mode
-n	          noexec	          # read commands in script, but dont execute; syntax check
-o OPT	      	                # Invoke the Option-Name option
-o posix	    POSIX	            # Change the behavior of Bash, or invoked script, to conform to POSIX standard.
-o pipefail	  pipefailure	      # Causes a pipeline to return the exit status of the last command in the pipe that returned a non-zero return value.
-p	          privileged	      # Script runs as "suid" (caution!)
-r	          restricted	      # Script runs in restricted mode
-s	          stdin	            # read commands from STDIN
-t	                	          # exit after first command
-u	          nounset	          # Attempt to use undefined variable outputs error message, and forces an exit
-v	          verbose	          # Print each command to stdout before executing it
-x	          xtrace	          # similar to -v, but expands commands

-	                	            # end of options flag; all other arguments are positional parameters
--	                	          # unset positional parameters. If arguments given (-- arg1 arg2), positional parameters set to arguments.
```

## special parameter

```sh
0        # expands to current shell e.g. $0 => "-bash"
!        # expands to the process ID of the job most recently placed into the background
$        # expands to process ID of the shell
-        # expands to current bash option flags, specified by the `set` or `bash -i`
#        # expands to number of positional parameters in decimal
@        # expands to positional parameters
*        # expands to positional parameters
```

## shell variables

```sh
_      # At shell startup, set to the pathname used to invoke the

BASH   # expands to the full filename used to invoke this instance
BASHOPTS
BASHPID
BASH_ALIASES
BASH_ARGC
BASH_ARGV
BASH_ARGV0
BASH_CMDS
BASH_COMMAND
BASH_EXECUTION_STRING
BASH_LINENO
BASH_LOADABLES_PATH
BASH_REMATCH
BASH_SOURCE
BASH_SUBSHELL
BASH_VERSINFO
BASH_VERSION
${BASH_VERSINFO[@]}     # as array

COMP_CWORD
COMP_KEY
COMP_LINE
COMP_POINT
COMP_TYPE
COMP_WORDBREAKS
COMP_WORDS
COPROC                # array variable (see Arrays below) created to hold the

DIRSTACK
EPOCHREALTIME
EPOCHSECONDS
EUID                  # expands to the effective user ID of the current user,

FUNCNAME
${FUNCNAME[@]}        # all functions including parents

GROUPS                # array variable containing the list of groups of which
HISTCMD
HOSTNAME
HOSTTYPE
LINENO                # Each time this parameter is referenced, the shell
MACHTYPE
MAPFILE
OLDPWD                # previous working directory as set by the cd command.
OPTARG                # value of the last option argument processed by the
OPTIND                # index of the next argument to be processed by the
OSTYPE                # Automatically set to a string that describes the operating

PIPESTATUS
PPID                  # process ID of the shell's parent.  This variable is
PWD                   # current working directory as set by the cd command.
RANDOM                # time this parameter is referenced, it expands to a
READLINE_LINE
READLINE_MARK
READLINE_POINT
REPLY                 # Set to the line of input read by the `read` builtin command 
SECONDS
SHELLOPTS
SHLVL                 # incremented by one each time an instance of bash is
SRANDOM
UID                   # expands to the user ID of the current user, initialized at

BASH_COMPAT
BASH_ENV
BASH_XTRACEFD

CDPATH The search path for the cd command.  This is a colon-
CHILD_MAX
COLUMNS
COMPREPLY
EMACS  If bash finds this variable in the environment when the
ENV    Expanded and executed similarly to BASH_ENV (see
EXECIGNORE
FCEDIT The default editor for the fc builtin command.
FIGNORE
FUNCNEST
GLOBIGNORE

HISTCONTROL
HISTFILE
HISTFILESIZE
HISTIGNORE
HISTSIZE
HISTTIMEFORMAT

HOME                  # home directory of the current user
HOSTFILE
IFS                   # Internal Field Separator that is used for word
IGNOREEOF
INPUTRC
INSIDE_EMACS
LANG                  # used to determine the locale category for any category not
LC_ALL                # overrides the value of LANG and any other
LC_COLLATE
LC_CTYPE
LC_MESSAGES
LC_NUMERIC
LC_TIME
LINES                 # Used by the select compound command to determine the
MAIL                  #
MAILCHECK
MAILPATH
OPTERR                # if set to the value 1, bash displays error messages
PATH                  # search path for commands.  It is a colon-separated
POSIXLY_CORRECT
PROMPT_COMMAND
PROMPT_DIRTRIM
PS0                   # value of this parameter is expanded (see PROMPTING
PS1                   # value of this parameter is expanded (see PROMPTING
PS2                   # value of this parameter is expanded as with PS1 and
PS3                   # value of this parameter is used as the prompt for the
PS4                   # value of this parameter is expanded as with PS1 and
SHELL                 # expands to the full pathname to the shell
TIMEFORMAT
TMOUT                 # if set to a value greater than zero, TMOUT is treated as
TMPDIR                # if set, bash uses its value as the name of a directory in
auto_resume
histchars
```

[[bash export]] [[env]] [[bash set]]

## usage

```sh
bash -c "echo 1"    # read command-string

bash --debugger

bash --debugger
PS4='+ ${BASH_SOURCE[0]} '
set -x ; __git_ps1 ; set +x

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
while [ "$COLOR" -lt "245" ]; do
  echo -ne "$COLOR: \\033[38;5;${color}mhello\\033[48;5;${color}mworld\\033[0m "
  [ $(( COLOR % 12 )) -eq "0" ] && { echo ""; }
  ((COLOR++));
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

- [[ash]], [[dash]], [[zsh]]
- [[bash prompt]]
- [[bash debugging]]
- [[bash parameter expansion]]
- [[bash test []]
- [[bash compgen]]
- [[bash time]]
- [[time]]
- [[bash variables]]
- [man7.org/linux/man-pages/man1/bash](https://man7.org/linux/man-pages/man1/bash.1.html)
- [gnu.org/software/bash/manual/bash](https://www.gnu.org/software/bash/manual/bash.html?#What-is-a-shell_003f)
- [tldp.org/html/internalvariables.html](https://www.tldp.org/LDP/abs/html/internalvariables.html)
- [whats-the-difference-between-shell-builtin-and-shell-keyword](https://askubuntu.com/a/590335/219213)
- [twitter.com/UnixToolTip/status/1220040690203348993](https://twitter.com/UnixToolTip/status/1220040690203348993)

