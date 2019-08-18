---
tags: [api]
title: elasticsearch
created: '2019-07-30T06:19:49.047Z'
modified: '2019-08-18T15:13:55.295Z'
---

# elasticsearch


### config
```sh
curl -s http://foo.bar.baz:9200/_cluster/settings
```

```sh
curl -XPUT http://foo.bar.baz:9200/_cluster/settings -d @- <<-EOF
{
	"transient": {	
	      "cluster.routing.allocation.disk.watermark.low": "90%",
	      "cluster.routing.allocation.disk.watermark.high": "90%"
	}
}
EOF
```

## Disk-based shard allocation

|config|default|explanation|
|--|--|--|
| `cluster.routing.allocation.disk.watermark.low` | 85% | will not allocate shards to nodes that have more than 85% disk used. |

| `cluster.routing.allocation.disk.watermark.high` | 90% | attempt to relocate shards away from a node whose disk usage is above 90%.|

| `cluster.routing.allocation.disk.watermark.flood_stage` | 95% | enforces a read-only index block (`index.blocks.read_only_allow_delete`) on every index that has one or more shards allocated on the node that has at least one disk exceeding the flood stage. This is a last resort to prevent nodes from running out of disk space. The index block must be released manually once there is enough disk space available to allow indexing operations to continue. |

## _cat
### indices

```sh
curl -s http://foo.bar.baz:9200/_cat/indices?v
```
```
health status index                           uuid                   pri rep docs.count docs.deleted store.size pri.store.size
green  open   .monitoring-kibana-2-2018.09.23 fQ-sbelpTKCARG-lSNifCA   1   1       8638            0      3.5mb          1.7mb
green  open   .monitoring-kibana-2-2018.06.19 7alGU2ULRvSoQfAY7HqqZw   1   1       8639            0      3.6mb          1.8mb
..
```

### allocation
```sh
curl -s http://foo.bar.baz:9200/_cat/allocation?v
```
```
shards disk.indices disk.used disk.avail disk.total disk.percent host                                         ip           node
  1041       55.7gb    75.7gb     17.8gb     93.5gb           80 elastic-monitor-1-data-1.node.ddev.domain.net 10.32.23.206 elastic-monitor-1-data-1
  1070       56.8gb    65.5gb       28gb     93.5gb           70 foo.bar.baz 10.32.23.207 elastic-monitor-1-data-2
    24                                                                                                                     UNASSIGNED
```
