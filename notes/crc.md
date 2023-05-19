---
tags: [container]
title: crc
created: '2023-03-13T11:11:53.909Z'
modified: '2023-05-17T08:00:54.634Z'
---

# crc

> `C`ode`R`eady`C`ontainers - tool that manages a local OpenShift 4.x cluster

## install

```sh
curl -LO https://developers.redhat.com/content-gateway/file/pub/openshift-v4/clients/crc/2.18.0/crc-macos-installer.pkg
installer -pkg crc-macos-installer.pkg -target /
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
- [[istioctl]]
- [[podman]]
- [[helm]]
- [[kubectl]]
- [[minikube]]
- [[installer]]
- [github.com/crc-org/crc](https://github.com/crc-org/crc)
- [github.com/crc-org/crc/wiki/Debugging-guide](https://github.com/crc-org/crc/wiki/Debugging-guide)
