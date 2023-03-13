---
tags: [container, container/docker]
title: docker-machine
created: '2019-07-30T06:19:49.044Z'
modified: '2020-03-13T12:52:16.889Z'
---

# docker-machine

> tool that lets you install Docker Engine on virtual hosts, and manage the hosts

## usage

```sh
# create on virtualbox
docker-machine create \
  -d virtualbox \                                 
  --virtualbox-boot2docker-url file:///home/boot2docker.iso \
  --virtualbox-disk-size=10000 \
  --virtualbox-memory=1024 \
  --engine-opt bip=10.20.30.40/24 \
  --engine-insecure-registry HOST:PORT \
  HOST

docker-machine \
  create \
  --driver vmwarevsphere \
  --vmwarevsphere-username=\"${ENV_VSPHERE_USERNAME}\" \
  --vmwarevsphere-password=\"${ENV_VSPHERE_PASSWORD}\" \
  --vmwarevsphere-vcenter=\"${ENV_VSPHERE_VCENTER}\" \
  --vmwarevsphere-datacenter=\"${ENV_VSPHERE_DATACENTER}\" \
  --vmwarevsphere-network=\"${ENV_VSPHERE_NETWORK}\" \
  --vmwarevsphere-cpu-count=\"${ENV_VSPHERE_CPU_COUNT}\" \
  --vmwarevsphere-memory-size=\"${ENV_VSPHERE_MEMORY_SIZE}\" \
  --vmwarevsphere-disk-size=\"${ENV_VSPHERE_DISK_SIZE}\" \
  --vmwarevsphere-datastore=\"${ENV_VSPHERE_DATASTORE}\" \
  --vmwarevsphere-hostsystem=\"${ENV_VSPHERE_HOSTSYSTEM}\" \
  --vmwarevsphere-boot2docker-url=\"${ENV_VSPHERE_BOOT2DOCKER_URL}\" \
  --engine-opt bip=\"${ENV_DOCKER_BIP}\" \
  --engine-opt dns=\"${ENV_DNS}\" \
  --engine-opt dns-search=\"${ENV_DOCKER_DOMAIN}\" \
  --engine-insecure-registry=\"${ENV_DOCKER_REGISTRY_ADDRESS1}\" \
  --engine-insecure-registry=\"${ENV_DOCKER_REGISTRY_ADDRESS2}\" \
  --tls-san=\"${DOCKER_HOST_FQDN}\" \
  ${DOCKER_HOST_FQDN}
```

## see also

- [[minikube]]
- [[docker]]
- [[vboxmanage]]
