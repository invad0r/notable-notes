---
tags: [database]
title: mysqldump
created: '2019-08-18T14:33:58.877Z'
modified: '2019-08-18T14:35:35.817Z'
---

# mysqldump

```sh
mysqldump -uUser -pUserPassword YourDatabaseName > wantedsqlfile.sql

mysqldump -uUser -pUserPassword YourDatabaseName < wantedsqlfile.sql
```

## encrypted
```sh
mysqldump -uUser -pPASS DATABASE | gzip > filename_to_compress.sql.gz				# For Export

gunzip < filename_to_compress.sql.gz | mysql -uUser -pPass DATABASE     		# For Import
```

## ignore tables
```sh
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
