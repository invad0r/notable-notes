---
tags: [shell/bash/builtin]
title: bash source
created: '2019-08-02T06:42:37.632Z'
modified: '2021-05-12T08:46:08.468Z'
---

# bash source

> execute commands from a file in the current shell

## usage
```sh
source foo.sh

. foo.sh


# determine if script is sourced or executed
#  ${0#-}: '#-' needed if sourced no path
if [ "$( basename ${0#-} )" == "$( basename ${BASH_SOURCE} )" ]; then COMMAND $@; fi

if [[ "${BASH_SOURCE[0]}" != "${0}" ]];                          then echo "sourcing script ${BASH_SOURCE[0]}"; fi

if [[ "$(basename ${BASH_SOURCE[0]})" == "${0}" ]];              then echo "calling function:" docker-connect "$@"; fi

[ "$_" != "$0" ] && echo "Script is being sourced" || echo "Script is a subshell"
```

## see also
- [[bash]]
- [[bash parameter expansion]]
