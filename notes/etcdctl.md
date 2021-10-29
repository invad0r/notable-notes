---
tags: [systemd]
title: etcdctl
created: '2019-09-24T04:24:49.035Z'
modified: '2021-10-20T09:07:49.855Z'
---

# etcdctl

> cli client for [[etcd]]

## install

`brew install etcd`

## usage

```sh
ETCDCTL_CACERT        # tmp/ca.pem
ETCDCTL_CERT          # tmp/cert.pem
ETCDCTL_KEY           # tmp/key.pem
ETCDCTL_ENDPOINTS     #
```

```sh
    --cacert=""                              # verify certificates of TLS-enabled secure servers using this CA bundle
    --cert=""                                # identify secure client using this TLS certificate file
    --command-timeout=5s                     # timeout for short running command (excluding dial timeout)
    --debug[=false]                          # enable client-side debug logging
    --dial-timeout=2s                        # dial timeout for client connections
-d, --discovery-srv=""                       # domain name to query for SRV records describing cluster endpoints
    --discovery-srv-name=""                  # service name to query when using DNS discovery
    --endpoints=[127.0.0.1:2379]             # gRPC endpoints
-h, --help[=false]                           # help for etcdctl
    --hex[=false]                            # print byte strings as hex encoded strings
    --insecure-discovery[=true]              # accept insecure SRV records describing cluster endpoints
    --insecure-skip-tls-verify[=false]       # skip server certificate verification
    --insecure-transport[=true]              # disable transport security for client connections
    --keepalive-time=2s                      # keepalive time for client connections
    --keepalive-timeout=6s                   # keepalive timeout for client connections
    --key=""                                 # identify secure client using this TLS key file
    --password=""                            # password for authentication (if this option is used, --user option shouldn't include password)
    --user=""                                # username[:password] for authentication (prompt if password is not supplied)
-w, --write-out="simple"                     # output format: json, protobuf, simple, table
```

```sh
etcdctl member list

etcdctl put foo "Hello World!"

etcdctl get foo
```

## see also

- [github.com/etcd-io/etcd/etcdctl](https://github.com/etcd-io/etcd/tree/main/etcdctl)
- [[kubectl]]
- [[consul]]
- [[zookeeper]]
- [[raft consesus algorithm]]
