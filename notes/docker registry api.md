---
tags: [container/docker, curl]
title: docker registry api
created: '2019-07-30T06:19:49.043Z'
modified: '2020-01-21T10:11:58.204Z'
---

# docker registry api

## usage
```sh
HEAD /v2/<name>/blobs/<digest>

/v2/path/manifests/0.0.2-SNAPSHOT
/v2/path/manifests/latest


curl --head  -XGET \
  -u user:pass \
  -k \
  -H "Accept: application/vnd.docker.distribution.manifest.v2+json" \
  https://foo.bar.baz/v2/path/manifests/0.0.2-SNAPSHOT
```

## see also
- [[docker]] 

