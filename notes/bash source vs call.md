---
tags: [bash]
title: bash source vs call
created: '2019-07-30T06:19:49.020Z'
modified: '2019-07-30T06:22:29.802Z'
---

# bash source vs call

```bash
[[ "${BASH_SOURCE[0]}" == "${0}" ]] && { echo "script ${BASH_SOURCE[0]} must be sourced."; exit 1; }
```
https://askubuntu.com/questions/53177/bash-script-to-set-environment-variables-not-working

```sh


# if [[ ${script_name} = ${this_script} ]] ; then
#     echo "running me directly"
# else
#     echo "sourced from ${script_name}"
# fi


#
#  ${0#-}: '#-' needed if sourced no path
if [ "$( basename ${0#-} )" == "$( basename ${BASH_SOURCE} )" ]; then
  docker-connect $@
fi

# if [[ "${BASH_SOURCE[0]}" != "${0}" ]]; then
# 	 echo "sourcing script ${BASH_SOURCE[0]}"
# fi
#
# if [[ "$(basename ${BASH_SOURCE[0]})" == "${0}" ]]; then
#   echo "calling function:" docker-connect "$@"
# fi



# [ "$_" != "$0" ] && echo "Script is being sourced" || echo "Script is a subshell"
#
# docker-connect $@


# bash ./docker-connect.sh
# ./docker-connect.sh



# docker-connect
# ./docker-connect
# bash ./docker-connect

```
