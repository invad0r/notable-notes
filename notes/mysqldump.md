---
tags: [database]
title: mysqldump
created: '2019-08-18T14:33:58.877Z'
modified: '2019-12-30T07:33:15.465Z'
---

# mysqldump

## usage
```sh
mysqldump -uUSER -pPASSWORD DBNAME > BACKUP.sql        # export

mysqldump -uUSER -pPASSWORD DBNAME < BACKUP.sql        # import


mysqldump -uUSER -pPASSWORD DBNAME | gzip > BACKUP.sql.gz				# for encrypted export

gunzip < BACKUP.sql.gz | mysql -uUSER -pPASSWORD DBNAME     		# for encrypted import

# ignore tables
mysqldump \
  --no-data \
  --ignore-table=DATABASE.jos_mpm \
  -h$HOST -u$USR -p$PWD \
  $DB > $(date +%Y-%m-%d)_SCHEME_$DB.sql

mysqldump \
  --no-create-info \
  --complete-insert \
  --ignore-table=DATABASE.jos_mpm \
  -h$HOST -u$USR -p$PWD \
  $DB > $(date +%Y-%m-%d)_DATA_$DB.sql
```

## see also
- [[mysql]]
- [[mongodump]]
