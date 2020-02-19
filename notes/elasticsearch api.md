---
tags: [curl, elasticsearch]
title: elasticsearch api
created: '2019-09-03T09:09:54.970Z'
modified: '2020-02-19T13:22:32.628Z'
---

# elasticsearch api

## usage
```sh
GET /_cat/nodes?h=h,diskAvail

GET /_cat/indices?v     # show all indices open and close !

GET /_cat/indices/some-index_392?v

GET /_cat/allocation?v

GET /_cat/allocation?v&pretty&h=node,disk.indices,disk.used,disk.avail,disk.total,disk.percent

GET /_cat/shards?v

GET /_cat/shards?v&h=index,shard,docs,store,node

?help
?bytes=b
#   `b` Bytes
#   `kb` Kilobytes
#   `mb` Megabytes
#   `gb` Gigabytes
#   `tb` Terabytes
#   `pb` Petabytes
?s=order:desc,index_patterns


GET /_nodes/process?pretty      # e.g. find out mlockall: true

GET /_nodes/_all/settings?flat_settings


GET /_cluster/health?pretty     # status

GET /_cluster/state/metadata

GET /_cluster/state/blocks


GET /_cluster/settings

PUT /_cluster/settings '{ "transient": { "cluster.routing.allocation.disk.watermark.low": "90%", "cluster.routing.allocation.disk.watermark.high": "90%" } }'
# disk-based shard allocation
# cluster.routing.allocation.disk.watermark.low         # (85%) will not allocate shards to nodes that have more than 85% disk used.
# cluster.routing.allocation.disk.watermark.high        # (90%) attempt to relocate shards away from a node whose disk usage is above 90%.
# cluster.routing.allocation.disk.watermark.flood_stage # (95%) enforces a read-only index block (`index.blocks.read_only_allow_delete`) on every index that has one or more shards allocated on the node that has at least one disk exceeding the flood stage. This is a last resort to prevent nodes from running out of disk space. The index block must be released manually once there is enough disk space available to allow indexing operations to continue.

PUT /_cluster/settings '{ "transient" :{ "cluster.routing.allocation.exclude._ip" : "10.20.30.40" } }'   # remove node from cluster
``` 
## see also
- [[curator]]
- [[ulimit]]
- [reference/current/cat.html](https://www.elastic.co/guide/en/elasticsearch/reference/current/cat.html)

