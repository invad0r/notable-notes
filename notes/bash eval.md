---
tags: [bash/built-in]
title: bash eval
created: '2019-07-30T06:19:49.005Z'
modified: '2020-01-10T10:17:09.296Z'
---

# bash eval

>`eval` - construct command by concatenating arguments

```sh
foo='ls -lah'
eval $foo
```

```sh
c="echo"; a1="Hello, "; a2="World!"; eval $c $a1 $a2
```

### usage

#### Perform var assignment using var names passed as string values.
```sh
key="mykey"
val="myval"
eval $key=$val

echo $mykey
myval
```


#### run cron command from file
```sh
# /etc/cron.d/repeatme
*/10 * * * * root program arg1 arg2

eval $( cut -d ' ' -f 6- /etc/cron.d/repeatme)
```

[The perils of Bash ‘eval’ - .debug - Medium](https://medium.com/dot-debug/the-perils-of-bash-eval-cc5f9e309cae)


#### building create command that respects quotes !
```sh
ENV_VSPHERE_HOSTSYSTEM='cluster/vhost01.domain.net'
ENV_VSPHERE_BOOT2DOCKER_URL='file:///Users/user/boot2docker.iso'

CMD=(
docker-machine create
--vmwarevsphere-username=\"${ENV_VSPHERE_USERNAME}\"
--vmwarevsphere-boot2docker-url=\"${ENV_VSPHERE_BOOT2DOCKER_URL}\"
foo.node.ddev.domain.net
)

eval ${CMD[@]}
```
