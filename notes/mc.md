---
title: mc
created: '2019-09-19T12:03:17.162Z'
modified: '2019-11-15T06:41:10.609Z'
---

# mc

> MinIO Client for cloud storage and filesystems

## install
```sh
GO111MODULE=on go get github.com/minio/mc                         # from source

curl -O https://dl.min.io/client/mc/release/linux-amd64/mc        # prebuilt binary
mv ./mc /usr/local/bin/ && chmod +x /usr/local/bin/mc

mc --autocompletion                                               # autocompletion !
```

## usage

```sh
mc config host add minio http://127.0.0.1:9000 FDKN3TTEO2B2OD6GZ84V exYeuqvdyuJSAlFJ0QW2+dLJEGznxq1dXZZDm6+C

mc config host list
```

## see also
- [[aws]]
