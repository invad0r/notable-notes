---
tags: [database]
title: mysqldump
created: '2019-08-18T14:33:58.877Z'
modified: '2022-02-02T09:34:01.761Z'
---

# mysqldump

> dump [[mysql]] database

## usage

```sh
mysqldump -uUSER -pPASSWORD DBNAME > BACKUP.sql        # export

mysqldump -uUSER -pPASSWORD DBNAME < BACKUP.sql        # import


mysqldump -uUSER -pPASSWORD DBNAME | gzip > BACKUP.sql.gz				# for encrypted export

gunzip < BACKUP.sql.gz | mysql -uUSER -pPASSWORD DBNAME     		# for encrypted import

mysqldump \
  --no-data \
  --ignore-table=DATABASE.jos_mpm `# ignore tables` \
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
- [[pg_dump]]
- [[pv]]
- [[zip]]
- [[gzip]]
- [[pigz]]
- [[date]]
