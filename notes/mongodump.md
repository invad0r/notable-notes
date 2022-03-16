---
tags: [database]
title: mongodump
created: '2019-11-14T08:15:23.493Z'
modified: '2022-02-04T08:24:31.530Z'
---

# mongodump

> `mongodump` - creates a binary export of the contents of a mongod database
> `mongorestore` - restores data from a mongodump database dump into a mongod or mongos
> `bsondump` - converts BSON dump files into JSON

## install

`brew tap mongodb/brew && brew install mongodb-database-tools`

## usage

```sh
mongodump --host=HOST --port=27017

mongodump --collection=COLLECTION --db=DATABASE


mongorestore --host=HOST --port=3017 --username=admin  --authenticationDatabase=admin /backup/mongodump-2019-01-01

mongorestore \
  --db DATABASE \
  --drop \
  --host=HOST \
  --port=27017 \
  --username=admin \
  --password="admin" \
  --authenticationDatabase=admin \
  /backup/mongodump-2019-01-01
```

## see also

- [docs.mongodb.com/database-tools](https://docs.mongodb.com/database-tools/)
- [[mongo]]
- [[mongoexport]]
- [[mysqldump]]
- [[pg_dump]]
