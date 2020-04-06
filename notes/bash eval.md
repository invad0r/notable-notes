---
tags: [bash/built-in]
title: bash eval
created: '2019-07-30T06:19:49.005Z'
modified: '2020-03-25T08:15:14.378Z'
---

# bash eval

>`eval` - construct command by concatenating arguments

## usage
```sh
foo='ls -lah'
eval $foo

c="echo"; a1="Hello, "; a2="World!"; eval $c $a1 $a2

# Perform var assignment using var names passed as string values.
key="mykey"
val="myval"
eval $key=$val

echo $mykey
myval

# building a command array because bash handles double-quotes differently
# on command execution - this can be problematic when variables contain spaces
# e.g. --network="${NETWORKD}"
#      --networkd=Docker Test
# here `Test` would be the next option instead of the argument of --network
cmd=(
  docker-machine \
  create \
  --driver vmwarevsphere \
  --vmwarevsphere-datacenter=\"${ENV_VSPHERE_DATACENTER}\" \
  --vmwarevsphere-network=\"${ENV_VSPHERE_NETWORK}\" \
  ${DOCKER_HOST_FQDN}
)
eval "${cmd[@]}"


# run cron command from file
# /etc/cron.d/repeatme
# */10 * * * * root program arg1 arg2
eval $( cut -d ' ' -f 6- /etc/cron.d/repeatme)
```


## see also
- [The perils of Bash ‘eval’ - .debug - Medium](https://medium.com/dot-debug/the-perils-of-bash-eval-cc5f9e309cae)
- [[docker-machine]]
- [[cut]]
- [[bash exec]]
