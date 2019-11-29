---
tags: [curl, elasticsearch]
title: elasticsearch api cluster
created: '2019-07-30T06:19:49.047Z'
modified: '2019-11-12T08:00:30.980Z'
---

# elasticsearch api cluster

## usage
```sh
GET /_cluster/health?pretty     # status

GET /_cluster/state/metadata
GET /_cluster/state/blocks



GET /_cluster/settings

PUT /_cluster/settings -d '{
  "transient": { 
    "cluster.routing.allocation.disk.watermark.low": "90%", 
    "cluster.routing.allocation.disk.watermark.high": "90%" 
    } 
}'


# remove node from cluster
curl -X PUT "host:9200/_cluster/settings" -H 'Content-Type: application/json' -d '{
  "transient" :{
      "cluster.routing.allocation.exclude._ip" : "10.20.30.40"
   }
}'
```

## disk-based shard allocation
```sh
cluster.routing.allocation.disk.watermark.low         # (85%) will not allocate shards to nodes that have more than 85% disk used.

cluster.routing.allocation.disk.watermark.high        # (90%) attempt to relocate shards away from a node whose disk usage is above 90%.

cluster.routing.allocation.disk.watermark.flood_stage # (95%) enforces a read-only index block (`index.blocks.read_only_allow_delete`) on every index that has one or more shards allocated on the node that has at least one disk exceeding the flood stage. This is a last resort to prevent nodes from running out of disk space. The index block must be released manually once there is enough disk space available to allow indexing operations to continue.
```

## see also
- [[elasticsearch api cat]]
- [[curator]]
