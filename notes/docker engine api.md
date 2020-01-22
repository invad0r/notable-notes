---
tags: [container/docker, curl]
title: docker engine api
created: '2019-08-20T09:42:39.909Z'
modified: '2020-01-21T10:10:48.927Z'
---

# docker engine api

## usage
```sh
-H unix:///var/run/docker.sock    # docker-daemon listen unix socket


curl --unix-socket /var/run/docker.sock http:/containers/json   # docker start container


curl -XPOST --unix-socket /var/run/docker.sock \
  -d '{"Image":"nginx"}' \
  -H 'Content-Type: application/json' \
  http://localhost/containers/create
#  { "Id": "fcb65c6147efcb6...7d65", "Warnings":null }

curl -XPOST --unix-socket /var/run/docker.sock \
  http://localhost/containers/fcb6...7d65/start


# events
docker run \                                      # run container 
  -ti \                                           # in interactive-mode
  -v /var/run/docker.sock:/var/run/docker.sock \  # bind mounts the docker.sock
  alpine sh

# inside container
curl --unix-socket /var/run/docker.sock http://localhost/events


# plugins
curl -XGET --unix-socket /run/docker/plugins/nfs.sock/Plugin.Activate \
  http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/Plugin.Activate


Post http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/Plugin.Activate
  : dial unix /run/docker/plugins/nfs.sock: connect: connection refused, retr

  http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/Plugin.Activate

%2F => /

curl -XGET --unix-socket /run/docker/plugins/nfs.sock \
  http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/Plugin.Activate  # /VolumeDriver.List
#  {"Implements": ["VolumeDriver"]}

curl -XGET --unix-socket /run/docker/plugins/nfs.sock \
  http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/VolumeDriver.List
#  {"Volumes":[]}

curl -XGET --unix-socket /run/docker/plugins/nfs.sock \
  http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/VolumeDriver.Path

EOF

curl -XGET --unix-socket /run/docker/plugins/nfs.sock \
  http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/VolumeDriver.Capabilities

{"Capabilities":{"Scope":"local"}}

curl -XGET --unix-socket /run/docker/plugins/nfs.sock \
  http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/VolumeDriver.Get

EOF


/Plugin.Activate
```

## see also
- [[curl]]
- [[unix socket]]
- [docker engine api](https://docs.docker.com/engine/api/v1.24/)
- https://github.com/docker/go-plugins-helpers/
