---
tags: [iac]
title: consul
created: '2019-08-28T09:45:08.570Z'
modified: '2020-04-30T14:58:11.555Z'
---

# consul

> consul is controlled via cli which takes a subcommand (`agent`, `members`..)

## usage
```sh
consul catalog nodes -http-addr=host              # working against remove consul-cluster 

consul catalog nodes -service=swarm-a -detailed


consul services deregister -id=SERVICEID          # find out service-id via curl api


consul watch -type=service -service=

consul watch -type=service -service=service



consul operator raft list-peers


consul members -http-addr=HOST

consul force-leave -http-addr=HOST MEMBER         # remove member

consul members -status=left -http-addr=HOST       # get left members


consul kv get -keys

consul kv get -http-addr=consul.foo.bar -recurse openstorage

consul kv get openstorage/cluster/database | jq


consul kv put footest @file.json        # from file

cat <<EOF | consul kv put footest -     # from here-doc
{"some": "val"}
EOF
```

## see also
- [[consul api]]
- [[watch]]
- [[awk]]
- [[etcdctl]]
- [[zookeeper]]
