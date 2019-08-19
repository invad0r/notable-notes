---
favorited: true
tags: [bash]
title: bash source vs execute
created: '2019-07-30T06:19:49.020Z'
modified: '2019-08-19T14:13:04.439Z'
---

# bash source vs execute

[[bash source]]

## determine if script is sourced or executed
```sh
#  ${0#-}: '#-' needed if sourced no path
if [ "$( basename ${0#-} )" == "$( basename ${BASH_SOURCE} )" ]; then COMMAND $@; fi

if [[ "${BASH_SOURCE[0]}" != "${0}" ]];                          then echo "sourcing script ${BASH_SOURCE[0]}"; fi

if [[ "$(basename ${BASH_SOURCE[0]})" == "${0}" ]];              then echo "calling function:" docker-connect "$@"; fi

[ "$_" != "$0" ] && echo "Script is being sourced" || echo "Script is a subshell"
```
