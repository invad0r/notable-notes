---
title: mc
created: '2019-09-19T12:03:17.162Z'
modified: '2020-08-05T07:27:46.134Z'
---

# mc

> MinIO Client for cloud storage and filesystems

## install
`GO111MODULE=on go get github.com/minio/mc` or `curl -O https://dl.min.io/client/mc/release/linux-amd64/mc`

## usage

```sh
mc --autocompletion            # setup autocompletion

mc config host list

mc config host add minio http://127.0.0.1:9000 FDKN3TTEO2B2OD6GZ84V exYeuqvdyuJSAlFJ0QW2+dLJEGznxq1dXZZDm6+C

mc ls BUCKET

mc mirror PATH BUCKET
```

## see also
- [[aws]]
- [[rsync]]
