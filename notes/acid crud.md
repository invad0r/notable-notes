---
tags: [Notebooks]
title: acid crud
created: '2019-08-18T16:14:42.254Z'
modified: '2020-08-24T12:24:59.821Z'
---

# acid crud

## acid
> set of properties that guarante reliable database transactions
```
A C I D
| | | └─ Durability
| | └─── Isolation
| └───── Consistency
└─────── Atomaticity
```

#### atomicity

> Transactions are composed of multiple statements. Atomicity guarantees that each transaction is treated as a single "unit", which either succeeds completely, or fails completely: if any of the statements constituting a transaction fails to complete, the entire transaction fails and the database is left unchanged.

#### consistency
> ensures that a transaction can only bring the database from one valid state to another - any data written to the database must be valid according to all defined rules, including constraints, cascades, triggers, and any combination thereof. This prevents database corruption by an illegal transaction, but does not guarantee that a transaction is correct.

#### isolation
> Transactions are often executed concurrently (e.g., multiple transactions reading and writing to a table at the same time). Isolation ensures that concurrent execution of transactions leaves the database in the same state that would have been obtained if the transactions were executed sequentially. 

#### durability
> guarantees that once a transaction has been committed, it will remain committed even in the case of a system failure (power outage or crash). This usually means that completed transactions are recorded in non-volatile memory

> ensure that the data is actually written on disk physically, preventing any loss of data in case of a sudden power outage

On POSIX systems, durability is achieved through `sync` operations: `fsync`, `fdatasync`, `aio_fsync`
`fsync` is intended to force a physical write of data from the buffer cache, and to assure that after a system crash/failure that all data up to the time of the `fsync` call is recorded on the disk.
`fdatasync()` does not necessarily update the meta-data associated with a file – such as the `last modified` date – but only the file data

## crud
> 4 basic functions of persistent storage
```
C R U D
| | | └─ Delete
| | └─── Update
| └───── Read
└─────── Ceate
```
                      
| CRUD-Operation   | SQL-92     | HTTP/REST        |
|--                |--          |--                |
| Create 	         |  `INSERT` 	| `PUT` or `POST`  |
| Read (Retrieve)  |  `SELECT`  | `GET`            |
| Update 	         |  `UPDATE`  | `PATCH` or `PUT` |
| Delete (Destroy) |  `DELETE`  | `DELETE`         |                                       

## see also
- [[rest api design]]
- [blog.httrack.com/../everything-you-always-wanted-to-know-about-fsync](http://blog.httrack.com/blog/2013/11/15/everything-you-always-wanted-to-know-about-fsync/)
- [lwn.net/postgresqls-fsync-surprise](https://lwn.net/Articles/752063/)
