---
tags: [database, Notebooks]
title: postgres vs mysql
created: '2023-05-04T11:13:23.713Z'
modified: '2023-05-04T11:25:14.422Z'
---

# postgres vs mysql

## main differences

- implementation of primary and secondary indexes
- how data is stored and updated

## b+ tree

- index is a datastructure (b+ tree)
- allows searching for keys
- keys in b+trees indexes are columns on the table

mysql "index organized tables"

- primary index value is the full row object with all the attributes
- secondary index the key is whatever column(s) you indexed and the value is a pointer to where the full row really live.  value of secondary index leaf pages are usually primary keys

postgres "heap organized tables"

- all indexes are secondary and all point to system managed tuple ids in data pages loaded in the heap

## process vs thread

MySQL uses threads 

- threads are lighter weight and share their parent process virtual memory address
- smaller thread control block (TCB)

Postgres uses processes 

- processes have overhead of dedicated virtual memory
- larger control block (PCB)

## see also

- [[mysql]]
- [[psql]]
- [medium.com/PostgresvsMySQL-fundamentalDifferences](https://medium.com/@hnasr/postgres-vs-mysql-5fa3c588a94e)


