---
tags: [shell/bash]
title: bash prompt
created: '2019-07-30T06:19:49.017Z'
modified: '2021-05-12T08:46:51.283Z'
---

# bash prompt

> `man bash` at the section `PROMPTING`

## usage
```sh
PS1="${GREEN}\u${DEFAULT}@${CYAN}${HOST}${DEFAULT}:${BLUE}\w${DEFAULT}${BRANCH}${GREY}${SETPROXY}${RED}${ERRPROMPT}${DEFAULT}\$ "

# PS2 - linebreak symbol e.g. ">"
PS2='> ' # used in multiline commands

# PS3 - select

# PS4 used with 'set -x'
PS4='$0.$LINENO+ '
PS4='+ ${BASH_SOURCE##*/}.${LINENO} ${FUNCNAME}: '


PROMPT_DIRTRIM=1          # see also prompt PS1="\W"

# You can set this in your bash shell config to flip a table whenever a command fails with a non-zero exit status.
PROMPT_COMMAND='[ $? -eq 0 ] || printf "(╯°□°）╯︵ ┻━┻\n"' 

prompt_command () {
  if [ $? -eq 0 ]; then # set an error string for the prompt, if applicable
    ERRPROMPT=" "
  else
    ERRPROMPT='->($?) '
  fi
}

# escape sequences
#  \a               an ASCII bell character (07)
#  \d               the  date  in "Weekday Month Date" format (e.g., "Tue May 26")
#  \D{format}       format is passed to strftime(3)  and  the  result  is inserted  into the prompt string; an empty format results in a locale-specific time representation.  The braces are required. e.g. '\D{%F %T}'
#                    %F - Equivalent to %Y-%m-%d (the ISO 8601 date format). (C99)
#                    %T - The time in 24-hour notation (%H:%M:%S). (SU)
#  \e               an ASCII escape character (033)
#  \h               the hostname up to the first `.'
#  \H               the hostname
#  \j               the number of jobs currently managed by the shell
#  \l               the basename of the shell's terminal device name
#  \n               newline
#  \r               carriage return
#  \s               the  name  of  the shell, the basename of $0 (the portion following the final slash)
#  \t               the current time in 24-hour HH:MM:SS format
#  \T               the current time in 12-hour HH:MM:SS format
#  \@               the current time in 12-hour am/pm format
#  \A               the current time in 24-hour HH:MM format
#  \u               the username of the current user
#  \v               the version of bash (e.g., 2.00)
#  \V               the release of bash, version + patch level (e.g., 2.00.0)
#  \w               the current working  directory,  with  $HOME  abbreviated with  a tilde (uses the value of the PROMPT_DIRTRIM variable)
#  \W               the basename of the current working directory, with $HOME abbreviated with a tilde
#  \!               the history number of this command
#  \#               the command number of this command
#  \\$               if the effective UID is 0, a #, otherwise a $
#  \nnn             the character corresponding to the octal number nnn
#  \\               a backslash
#  \[               begin  a sequence of non-printing characters, which could be used to embed a terminal  control  sequence  into  the prompt
#  \]               end a sequence of non-printing characters


#   d         date in "Weekday Month Date" format (e.g., "Tue May 26")
#   e         an ASCII escape character (033)
#   h         hostname up to the first .
#   H         full hostname
#   j         number of jobs currently run in background
#   l         basename of the shells terminal device name
#   n         newline
#   r         carriage return
#   s         name of the shell, the basename of $0 (the portion following the final slash)
#   t         current time in 24-hour HH:MM:SS format
#   T         current time in 12-hour HH:MM:SS format
#   @         current time in 12-hour am/pm format
#   A         current time in 24-hour HH:MM format
#   u         username of the current user
#   v         version of bash (e.g., 4.00)
#   V         release of bash, version + patch level (e.g., 4.00.0)
#   w         Complete path of current working directory
#   W         basename of the current working directory
#   !         history number of this command
#   #         the command number of this command
#   $         if the effective UID is 0, a #, otherwise a $
#   nnn       character corresponding to the octal number nnn
#   \         a backslash
#   [         begin a sequence of non-printing characters, which could be used to embed a terminal control sequence into the prompt
#   ]         end a sequence of non-printing characters
```

## see also
- [[bash]]
- [[bash select]]
- [[bash debugging]]
- [bneijt.nl/add-a-timestamp-to-your-bash-prompt/](https://bneijt.nl/blog/post/add-a-timestamp-to-your-bash-prompt/)
- [My new favorite Bash prompt - BrettTerpstra.com](http://brettterpstra.com/2009/11/17/my-new-favorite-bash-prompt/)
