---
tags: [bash]
title: bash prompt
created: '2019-07-30T06:19:49.017Z'
modified: '2019-07-30T06:22:29.799Z'
---

# bash prompt

```sh
# PS1 - 
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
```


```sh
prompt_command () {
    if [ $? -eq 0 ]; then # set an error string for the prompt, if applicable
        ERRPROMPT=" "
    else
        ERRPROMPT='->($?) '
    fi

```
[My new favorite Bash prompt - BrettTerpstra.com](http://brettterpstra.com/2009/11/17/my-new-favorite-bash-prompt/)
