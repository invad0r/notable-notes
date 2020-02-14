---
title: dockerd
created: '2020-01-03T13:18:17.258Z'
modified: '2020-02-14T10:32:24.124Z'
---

# dockerd

> docker daemon

## usage
```sh
systemctl stop docker

vim /etc/default/docker

  DOCKER_OPTS="-H tcp://0.0.0.0:2375 -H unix:///var/run/docker.sock"
  

vim /lib/systemd/system/docker.service
  ..
  ExecStart=/usr/bin/dockerd -H tcp://0.0.0.0:2375 -H unix://
  

  
iptables -A INPUT -p tcp --dport 2375 -j ACCEPT   # ! not safe for restart


systemctl start docker
```

## see also
- [[docker]]
- [[systemctl]]
- [[iptables]]
