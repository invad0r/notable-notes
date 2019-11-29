---
tags: [curl, elasticsearch]
title: elasticsearch api cat
created: '2019-09-03T09:09:54.970Z'
modified: '2019-11-12T07:07:17.908Z'
---

# elasticsearch api cat

## usage
```sh
GET /_cat/nodes?h=h,diskAvail


GET /_cat/indices?v     # show all indices open and close !

GET /_cat/indices/some-index_392?v


GET /_cat/allocation?v

GET /_cat/allocation?v&pretty&h=node,disk.indices,disk.used,disk.avail,disk.total,disk.percent


GET /_cat/shards?v

GET /_cat/shards?v&h=index,shard,docs,store,node
```

## help
```sh
?help

?bytes=b
#   `b` Bytes
#   `kb` Kilobytes
#   `mb` Megabytes
#   `gb` Gigabytes
#   `tb` Terabytes
#   `pb` Petabytes

?s=order:desc,index_patterns
```

## see also
- [[elasticsearch api cluster]]
- [reference/current/cat.html](https://www.elastic.co/guide/en/elasticsearch/reference/current/cat.html)
