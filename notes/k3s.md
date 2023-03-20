---
tags: [container]
title: k3s
created: '2021-10-15T07:36:40.840Z'
modified: '2023-03-16T08:49:37.052Z'
---

# k3s

> lightweight kubernetes distro aimed for developers & IoT devices

## usage

```sh
k3s server \
  --cluster-reset \
  --cluster-reset-restore-path=/var/lib/rancher/k3s/server/db/snapshots/etcd-snapshot-k3s-server-1-1643738640 \
  --node-external-ip 192.168.56.11 \
  --node-ip 192.168.56.11

systemctl start k3s
systemctl stop k3s

systemctl daemon-reload && systemctl restart k3s
```

## see also

- [[k3sup]]
- [[kubectl]]
- [[k3d]]
- [[k0s]]
- [[k9s]]
- [[kind]]
- [[vagrant]]
- [[microk8s]]
- [[minikube]]
- [github.com/k3s-io/k3s](https://github.com/k3s-io/k3s)
- [[command-not-found]]
