---
tags: [container, container/docker]
title: docker
created: '2019-07-30T06:19:49.045Z'
modified: '2020-03-02T10:13:24.723Z'
---

# docker

> A self-sufficient runtime for containers

## usage
```sh
# Environment variables
# DOCKER_API_VERSION                The API version to use (e.g. 1.19)
# DOCKER_CONFIG                     The location of your client configuration files
# DOCKER_CERT_PATH                  The location of your authentication keys
# DOCKER_CLI_EXPERIMENTAL           Enable experimental features for the cli (e.g. enabled or disabled)
# DOCKER_DRIVER                     The graph driver to use
# DOCKER_HOST                       Daemon socket to connect to
# DOCKER_NOWARN_KERNEL_VERSION      Prevent warnings that your Linux kernel is unsuitable for Docker
# DOCKER_RAMDISK                    If set this will disable ‘pivot_root’
# DOCKER_STACK_ORCHESTRATOR         Configure the default orchestrator to use when using docker stack management commands
# DOCKER_TLS                        When set Docker uses TLS
# DOCKER_TLS_VERIFY                 When set Docker uses TLS and verifies the remote
# DOCKER_CONTENT_TRUST              When set Docker uses notary to sign and verify images. 
#                                   Equates to --disable-content-trust=false for build, create, pull, push, run
# DOCKER_CONTENT_TRUST_SERVER       The URL of the Notary server to use. This defaults to the same URL as the registry
# DOCKER_HIDE_LEGACY_COMMANDS       When set, Docker hides “legacy” top-level commands (such as docker rm, and docker pull)
# DOCKER_TMPDIR                     Location for temporary Docker files

# connect remote dockerd securely
export DOCKER_TLS_VERIFY=1 \
  DOCKER_HOST=tcp://10.32.23.187:2376 \
  DOCKER_API_VERSION=1.38 \
  DOCKER_CERT_PATH=/Users/user/certs

# set prompt 
docker exec -it --env 'PS1=[consul]\w \$ ' consul ash
#   --env 'PS1=['$ENV_KEY'] \s-\v\$ '


docker run -it -v /var/run/docker.sock:/var/run/docker.sock ubuntu:latest \
  sh -c "apt-get update ; apt-get install docker.io -y ; bash"

docker run --rm httpd:2.4-alpine htpasswd -nbB admin PASSWORD | cut -d ":" -f 2    # generate password



# filter
docker ps -a --no-trunc --filter name=^/foo$            # list container who's name is "/foo"

docker image ls --filter label=org.opencontainers.image.vendor="Elastic"


docker logs nginx 2>&1 | grep "127."    # debugging: grepping logs with 2>&1


docker events


docker inspect 0                        # low level information about container

docker inspect 16e3103698c2 | jq '.[] | .Config .Image'

docker inspect --format '{{.State.Running}}' $CONTAINER_ID    # container running

docker inspect --format '{{ index .Config.Labels "com.foo.bar" }}' foo   # index function: can lookup arbitrary strings in the map

docker inspect --format "{{.State.Status}}" $container_id &>/dev/null


docker stats $(docker inspect -f '{{.Name}}' $(docker ps -q) | cut -c 2-)

docker stats $(docker ps --format={{.Names}})


docker swarm update --task-history-limit=1        # swarm task-history

docker node inspect $(docker node ls --format '{{.Hostname}}')| jq -r '.[].ManagerStatus.Addr'    # get node ip


docker network inspect -f '{{range $container_id, $container_def := .Containers}} {{$container_id}}^{{index $container_def "Name"}} {{end}}'

docker network disconnect -f $network_name $container_name
```

## see also
- [linux - How to clear Docker task history - Stack Overflow](https://stackoverflow.com/questions/42364695/how-to-clear-docker-task-history#)
- [Starting container failed: Address already in use · GitHub](https://github.com/moby/moby/issues/31698#issuecomment-320294893)
- [Use the Docker command line \| Docker Documentation](https://docs.docker.com/engine/reference/commandline/cli/#environment-vairables)
