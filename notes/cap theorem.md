---
tags: [Notebooks]
title: cap theorem
created: '2021-12-26T14:43:50.251Z'
modified: '2023-05-24T14:42:19.842Z'
---

# cap theorem

> aka `Brewer's theorem`

```
C A P
| | └─ consistency
| └─── availability
└───── partition
```

@startuml
(consistency) -- (availability)
(partition) - (availability)
(consistency) - (partition)
@enduml

## used by:

- `rabbitmq` Clustering: CP
- Federation/shovel: AP


`A.C.I.D.` vs `B.A.S.E.`

CA-DataBase: postgres -> single node

AP-DataBase: avail. + part. tol. -> cassandra, couchbase, (nosql eventual consistency)

CP-DataBase: spanner, cockroach

mvcc mutliversionconcurencycontrol

## see also

- [[erlang]], [[rabbitmqctl]]
- [infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed/](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed/)
