---
tags: [api, container/docker, curl]
title: docker api
created: '2019-08-20T09:42:39.909Z'
modified: '2020-09-02T17:29:03.759Z'
---

# docker api

## usage
```sh
-H "unix:///var/run/docker.sock"    # docker-daemon listen unix socket


curl --unix-socket /var/run/docker.sock \
  "http://./debug/pprof/goroutine?debug=2"    # dump stacktrace

curl --unix-socket /var/run/docker.sock \
  "http://containers/json"                       # start container


curl -XPOST --unix-socket /var/run/docker.sock \
  -H 'Content-Type: application/json' \
  -d '{"Image":"nginx"}' \
  "http://localhost/containers/create"
#  { "Id": "fcb65c6147efcb6...7d65", "Warnings":null }

curl -XPOST --unix-socket /var/run/docker.sock \
  http://localhost/containers/fcb6...7d65/start


# get events from inside container
docker run -ti \                                  # run in interactive-mode 
  -v /var/run/docker.sock:/var/run/docker.sock \  # (1) bind mounts the docker.sock
  alpine sh
curl --unix-socket /var/run/docker.sock \         # (2) get events
  "http://localhost/events"


curl -XGET --unix-socket /run/docker/plugins/nfs.sock/Plugin.Activate \
  "http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/Plugin.Activate"

curl -XGET --unix-socket /run/docker/plugins/nfs.sock \
  "http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/Plugin.Activate"

curl -XGET --unix-socket /run/docker/plugins/nfs.sock \
  "http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/VolumeDriver.List"

curl -XGET --unix-socket /run/docker/plugins/nfs.sock \
  "http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/VolumeDriver.Path"

curl -XGET --unix-socket /run/docker/plugins/nfs.sock \
  "http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/VolumeDriver.Capabilities"

curl -XGET --unix-socket /run/docker/plugins/nfs.sock \
  "http://%2Frun%2Fdocker%2Fplugins%2Fnfs.sock/VolumeDriver.Get"


/Plugin.Activate
```

## see also
- [[curl]]
- [[unix socket]]
- [docs.docker.com/engine/api](https://docs.docker.com/engine/api/v1.24/)
- https://github.com/docker/go-plugins-helpers/
