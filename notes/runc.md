---
title: runc
created: '2020-03-12T13:59:22.450Z'
modified: '2020-03-12T14:01:21.692Z'
---

# runc

> runc is a CLI tool for spawning and running containers according to the OCI specification.

## usage
```sh
runc create mycontainerid       # run as root

runc list                       # view the container is created and in the "created" state

runc start mycontainerid        # start the process inside the container

runc list                       # after 5 seconds view that the container has exited and is now in the stopped state

runc delete mycontainerid       # now delete the container
```

## see also
- [[docker]]
- [github.com/opencontainers/runc](https://github.com/opencontainers/runc)
