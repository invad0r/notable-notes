---
tags: [database]
title: psql
created: '2019-07-30T06:19:49.220Z'
modified: '2021-05-11T07:29:12.785Z'
---

# psql

## install
`apt install postgresql`

## usage
```sh
psql DBNAME USER

psql DBNAME -U USER -d DATABASE

psql -U USER -d DATABASE -c "SELECT * FROM some_table"
```

```sql
\?                -- help for psql commands
\h                -- help for SQL commands

\conninfo         -- information about the current database connection

\list             -- list all databases

\connect DATABASE -- switch to database

\dt               -- list all tables in the current database

\z                -- list all of the tables, views, and sequences in the database

\q                -- exit the psql program

\d+ table         -- describe
DESCRIBE TABLE

\x auto         -- output format

-- init
CREATE DATABASE bookstore;
CREATE USER bookstore_user WITH ENCRYPTED PASSWORD 'secret';
GRANT ALL PRIVILEGES ON DATABASE bookstore TO bookstore_user;
GRANT ALL PRIVILEGES ON TABLE books TO bookstore_user;

psql "dbname=bookstore host=localhost user=bookstore_user password=secret port=5432"
sslmode=require


BEGIN; UPDATE users SET admin = 't' WHERE id = '38'; select admin from users where id = '38'; ROLLBACK; -- dryrun


SELECT pg_size_pretty( pg_database_size('DATABASE') );    -- get db size
```

## see also
- [[pg_dump]]
- [PSQL-META-COMMANDS](https://www.postgresql.org/docs/current/static/app-psql.html#APP-PSQL-META-COMMANDS)
- [alternate-output-format-for-psql](https://stackoverflow.com/questions/9604723/alternate-output-format-for-psql)
- [[mongo]]
- [[mysql]]
