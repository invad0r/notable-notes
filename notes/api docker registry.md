---
tags: [api, container/docker, curl]
title: api docker registry
created: '2019-07-30T06:19:49.043Z'
modified: '2022-02-01T14:44:12.978Z'
---

# api docker registry 

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

