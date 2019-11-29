---
tags: [database]
title: sqlite
created: '2019-07-30T06:19:49.240Z'
modified: '2019-11-14T09:02:46.947Z'
---

# sqlite

## usage
```sh
sqlite3 grafana.db    # create or us database
```
    
```sql
.open ./var/lib/grafana/grafana.db

.databases

.tables

.schema

.mode column

.headers on
```

```sql
drop table import;
-- The VACUUM command rebuilds the database file, repacking it into a minimal amount of disk space
vacuum;
```

### import csv
```sql
.mode csv
-- table_name is `import`
.import shakespeare_data.csv import
```

### inline text search - FTS5
```sql
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
