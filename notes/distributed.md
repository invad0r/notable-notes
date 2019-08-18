---
tags: [Notebooks]
title: distributed
created: '2019-07-30T06:19:49.038Z'
modified: '2019-07-30T07:03:07.835Z'
---

# distributed

## quorum

> minimum number of votes that a distributed transaction has to optain to be allowed to perform operation in a distributed system
> => enforces consistent operations in a distributed system

### CAP theorem aka `Brewer's theorem`
@startuml
(consistency) -- (availability)
(partition) - (availability)
(consistency) - (partition)
@enduml

#### usage:
- `rabbitmq` Clustering: CP
- Federation/shovel: AP
