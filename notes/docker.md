---
tags: [container, container/docker]
title: docker
created: '2019-07-30T06:19:49.045Z'
modified: '2019-09-24T10:19:48.748Z'
---

# docker

> A self-sufficient runtime for containers

## Environment variables
```sh
DOCKER_API_VERSION            # The API version to use (e.g. 1.19)
DOCKER_CONFIG                 # The location of your client configuration files.
DOCKER_CERT_PATH              # The location of your authentication keys.
DOCKER_CLI_EXPERIMENTAL       # Enable experimental features for the cli (e.g. enabled or disabled)
DOCKER_DRIVER                 # The graph driver to use.
DOCKER_HOST                   # Daemon socket to connect to.
DOCKER_NOWARN_KERNEL_VERSION  # Prevent warnings that your Linux kernel is unsuitable for Docker.
DOCKER_RAMDISK                # If set this will disable ‘pivot_root’.
DOCKER_STACK_ORCHESTRATOR     # Configure the default orchestrator to use when using docker stack management commands.

DOCKER_TLS                    # When set Docker uses TLS.
DOCKER_TLS_VERIFY             # When set Docker uses TLS and verifies the remote.

DOCKER_CONTENT_TRUST          # When set Docker uses notary to sign and verify images. 
                              # Equates to --disable-content-trust=false for build, create, pull, push, run.
DOCKER_CONTENT_TRUST_SERVER   # The URL of the Notary server to use. This defaults to the same URL as the registry.

DOCKER_HIDE_LEGACY_COMMANDS   # When set, Docker hides “legacy” top-level commands (such as docker rm, and docker pull)
DOCKER_TMPDIR                 # Location for temporary Docker files.
```


## connect remote dockerd securely
```sh
export \
  DOCKER_TLS_VERIFY=1 \
  DOCKER_HOST=tcp://10.32.23.187:2376 \
  DOCKER_API_VERSION=1.38 \
  DOCKER_CERT_PATH=/Users/user/certs
  
docker system info --format '{{ json . }}'
```
```sh
export DOCKER_TLS_VERIFY=1 DOCKER_CERT_PATH="../certs/ca" DOCKER_HOST=tcp://host:2376
```

## see also
- [Use the Docker command line \| Docker Documentation](https://docs.docker.com/engine/reference/commandline/cli/#environment-vairables)
