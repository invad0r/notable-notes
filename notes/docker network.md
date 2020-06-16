---
tags: [container, container/docker]
title: docker network
created: '2019-07-30T06:19:49.041Z'
modified: '2020-05-11T08:10:34.103Z'
---

# docker network

## docker overlay network
- network namepsace
- XVLAN
- Netlink
- distributed KV-Store (consul)
```
┌─────────────┐              (VXLAN Tunnel Endpoint)
│ container ┌─┴────┐   ┌─────┐     ┌──────┐     ┌───────────────┐
└───────────┤ veth ├───┤ br0 ├─────┤ VTEP ├─────┤  vxlan tunnel │
            └──────┘   └─────┘     └──────┘     └───────────────┘
                   ┌───────────────────┘
VTEP encapsulates Frames by adding VXLAN-Header

  ┌────────────────┬──────────────┐
  │ Ethernet Frame │ VXLAN-Header │
  └────────────────┴──┬───────────┘
                      └─ VNID
```
`L3` segement routing IP (`network`)
`L2` broadcast MAC (`Datalink`)

## usage
```sh
## debugging inside container
docker exec container ip addr show

docker exec container ip route

# create entwork and attach container
docker network create -d bridge --subnet 1.2.3.0/24 my_bridge

docker network create --driver bridge --subnet 192.168.100.0/24 --ip-range 192.168.100.0/24 my-bridge-network

docker run -itd --name c2 --net my_bridge busybox sh

docker run -itd --name c3 --net my_bridge --ip 20.10.0.254 busybox sh

docker run -itd --name c3 --net my_bridge --ip 10.23.6.33 busybox sh

docker run -d --name C2 --net my_bridge -p 5000:80 nginx

docker run -itd --name c1 busyboy sh

docker run -itd --name c1-1 --network host busybox sh
```

## see also
- [[brctl]]
- [[nat]]
- [[servicemesh]]
- [Docker Reference Architecture - success.docker.com](http://success.docker.com/article/networking)
- [Demystifying Docker overlay networking – nigelpoulton.com](http://blog.nigelpoulton.com/demystifying-docker-overlay-networking/)

