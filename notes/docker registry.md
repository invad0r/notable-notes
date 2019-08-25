---
tags: [container/docker, curl]
title: docker registry
created: '2019-07-30T06:19:49.043Z'
modified: '2019-08-20T09:45:09.659Z'
---

# docker registry

### endpoints
```sh
HEAD /v2/<name>/blobs/<digest>

/v2/path/manifests/0.0.2-SNAPSHOT
/v2/path/manifests/latest
```

### curl
```sh
curl \
  --head \
  -XGET \
  -u user:pass \
  -k \
  -H "Accept: application/vnd.docker.distribution.manifest.v2+json" \
  https://foo.bar.baz/v2/path/manifests/0.0.2-SNAPSHOT
```


