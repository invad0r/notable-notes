---
title: osd
created: '2019-10-18T09:40:37.238Z'
modified: '2021-10-31T14:56:47.594Z'
---

# osd

> openstorage cli


## usage
```sh
osd cluster status


osd nfs enumerate | jq '.[].device_path'

osd nfs enumerate | jq -r '.[]| "\(.id) \(.locator.name)"'


osd -d --nodeid %H --clusterid CLUSTERNAME --sdkport 9101 --kvdb consul-kv://localhost:8500 --file /etc/config.yaml
```

## see also
- https://github.com/libopenstorage/openstorage
- [[nfs]]
- [[jq]]
- [[findmnt]]
- [[lsof]]
