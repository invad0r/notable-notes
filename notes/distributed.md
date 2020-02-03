---
tags: [Notebooks]
title: distributed
created: '2019-07-30T06:19:49.038Z'
modified: '2020-02-01T08:28:58.539Z'
---

# distributed

## quorum

> minimum number of votes that a distributed transaction has to optain to be allowed to perform operation in a distributed system
> => enforces consistent operations in a distributed system

## CAP theorem 
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
