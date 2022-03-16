---
tags: [database]
title: sqlite
created: '2019-07-30T06:19:49.240Z'
modified: '2022-01-31T18:03:49.262Z'
---

# sqlite

> c lib that implements small, fast, self-contained, high-reliability, full-featured, sql-database engine

## install

```sh
zypper install sqlite3
```

## usage

```sh
sqlite3 DATABASE.db    # create or us database

cat <<EOT > ~/.sqliterc
.mode column
.headers on
.separator ROW "\n"
.nullvalue NULL
EOT
```
    
```sql
.open ./PATH/TO/DB      -- open from sqlite-shell

.databases              -- list dbs

.tables                 -- list tables

.schema TABLE           -- describe table

.mode column            -- change output format
.headers on
.mode tabs      


drop table import;

vacuum;                 -- rebuilds database file, repacking into a minimal amount of disk space


.mode csv                             -- import csv
.import shakespeare_data.csv import   -- table_name is `import`


CREATE VIRTUAL TABLE playsearch USING fts5(playsrowid, text);   -- inline text search - FTS5, a virtual table module
INSERT INTO playsearch SELECT rowid, text FROM plays;
SELECT rowid, text FROM playsearch WHERE text MATCH "whether tis nobler"; -- Now we can search for our soliloquy
```

## see also

- [[mysql]]
- [[psql]]
- [[mongo]]
- [[fossil]]
- [[c]]
