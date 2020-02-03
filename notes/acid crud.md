---
tags: [Notebooks]
title: acid crud
created: '2019-08-18T16:14:42.254Z'
modified: '2020-02-01T08:31:03.545Z'
---

# acid crud

## acid
> set of properties that guarante reliable databse transactions
```
A C I D
| | | └─ Durability
| | └─── Isolation
| └───── Consistency
└─────── Automaticity
```

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

[[rest api design]]

