---
title: md5sum
created: '2019-10-11T06:16:32.667Z'
modified: '2019-10-11T06:21:04.301Z'
---

# md5sum

> compute and check MD5 message digest

## usage
```sh
md5sum file.log.tar.gz

echo 'eb6d6eddb5bcb5c4229a45b31f209b0d  file.log.tar.gz' | md5sum -c -

md5sum -c <filename>.zip.md5 <filename>.zip
```
## see also
- [[sha256sum]]
- [[openssl]]

