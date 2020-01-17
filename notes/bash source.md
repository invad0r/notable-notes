---
tags: [bash/built-in]
title: bash source
created: '2019-08-02T06:42:37.632Z'
modified: '2020-01-16T08:08:56.952Z'
---

# bash source

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
