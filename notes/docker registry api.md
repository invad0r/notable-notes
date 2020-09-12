---
tags: [api, container/docker, curl]
title: docker registry api
created: '2019-07-30T06:19:49.043Z'
modified: '2020-09-02T17:29:03.788Z'
---

# docker registry api

## usage
```sh
HEAD /v2/<name>/blobs/<digest>

GET /v2/path/manifests/0.0.2-SNAPSHOT

GET /v2/path/manifests/latest

curl --head -k -H "Accept: application/vnd.docker.distribution.manifest.v2+json" \
  -u user:pass "https://foo.bar.baz/v2/path/manifests/0.0.2-SNAPSHOT"
```

## see also
- [[docker]]
- [[nexus api]]

