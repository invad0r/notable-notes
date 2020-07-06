---
tags: [database]
title: sqlite
created: '2019-07-30T06:19:49.240Z'
modified: '2020-07-02T06:35:07.614Z'
---

# sqlite

> c library that implements small, fast, self-contained, high-reliability, full-featured, sql-database engine

## usage
```sh
sqlite3 DATABASE.db    # create or us database
```
    
```sql
.open ./var/lib/grafana/grafana.db

.databases

.tables

.schema

.mode column

.headers on


drop table import;
-- The VACUUM command rebuilds the database file, repacking it into a minimal amount of disk space
vacuum;

-- import csv
.mode csv
-- table_name is `import`
.import shakespeare_data.csv import


-- inline text search - FTS5
-- FTS5 is an SQLite virtual table module that provides full-text search functionality
CREATE VIRTUAL TABLE playsearch USING fts5(playsrowid, text);
INSERT INTO playsearch SELECT rowid, text FROM plays;

-- Now we can search for our soliloquy:
SELECT rowid, text FROM playsearch WHERE text MATCH "whether tis nobler";
```

## see also
- [[mysql]]
- [[psql]]
- [[mongo]]
- [[fossil]]
- [[c]]
