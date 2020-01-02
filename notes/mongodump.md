---
tags: [database]
title: mongodump
created: '2019-11-14T08:15:23.493Z'
modified: '2019-12-30T07:32:18.096Z'
---

# mongodump

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
- [[mongo]]
- [[mysqldump]]
