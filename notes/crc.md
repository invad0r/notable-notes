---
tags: [container]
title: crc
created: '2023-03-13T11:11:53.909Z'
modified: '2023-03-22T10:24:05.502Z'
---

# crc

> tool that manages a local OpenShift 4.x cluster

## install

```sh
```

## option

```sh
-h, --help                # help for crc
    --log-level string    # log level [debug | info | warn | error]
```

## usage

```sh
crc setup                 # set up your host operating system for the OpenShift Local virtual machine

crc start                 # create a minimal OpenShift 4 cluster locally

crc bundle                # Manage CRC bundles
crc cleanup               # Undo config changes
crc completion            # Generate the autocompletion script for the specified shell
crc config                # Modify crc configuration
crc console               # Open the OpenShift Web Console in the default browser
crc delete                # Delete the instance
crc help                  # Help about any command
crc ip                    # Get IP address of the running OpenShift cluster
crc oc-env                # Add the 'oc' executable to PATH
crc podman-env            # Setup podman environment
crc status                # Display status of the OpenShift cluster
crc stop                  # Stop the instance
crc version               # print version information
```

## see also

- [[oc]]
- [[helm]]
- [[kubectl]]
- [[minikube]]
