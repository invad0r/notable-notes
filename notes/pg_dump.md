---
title: pg_dump
created: '2021-03-15T07:59:51.829Z'
modified: '2022-08-22T11:50:21.341Z'
---

# pg_dump

> extract a postgresql database into a script file or other archive file

## environment

```sh
PGDATABASE        # -
PGHOST            # -
PGOPTIONS         # -
PGPORT            # -
PGUSER            # -
PGSSLMODE         # determines whether or with what priority a secure SSL TCP/IP connection will be negotiated with the server. There are six modes:
                  #   disable 	    only try a non-SSL connection
                  #   allow 	      first try a non-SSL connection; if that fails, try an SSL connection
                  #   prefer        (default) 	first try an SSL connection; if that fails, try a non-SSL connection
                  #   require 	    only try an SSL connection. If a root CA file is present, verify the certificate in the same way as if verify-ca was specified
                  #   verify-ca 	  only try an SSL connection, and verify that the server certificate is issued by a trusted CA
                  #   verify-full 	only try an SSL connection, verify that the server certificate is issued by a trusted CA and that the server host name matches that in the certificate
```

## usage

```sh
pg_dump -h HOST -p PORT -U USER -d DATABASE > FILE.dump

pg_dump DATABASE > db.sql                               # dump database called DATABASE into sql-script file

psql -d NEWDB -f db.sql                                 # reload script into a (freshly created) database: NEWDB

pg_dump -Fc DATABASE > db.dump                          # dump database into custom-format archive file
pg_dump -Fd DATABASE -f dumpdir                         # dump database into directory-format archive
pg_dump -Fd DATABASE -j 5 -f dumpdir                    # dump database into directory-format archive in parallel with 5 worker jobs

pg_restore -d NEWDB db.dump                             # reload an archive file into a (freshly created) database: NEWDB

pg_dump -t TABLE DATABASE > db.sql                      # dump a single table
pg_dump -t "\"MixedCaseName\"" DATABASE > mytab.sql     # specify upper-/mixed-case name in -t and related switches, name needs to be double-quoted else it will be folded to lower case (see Patterns)

pg_dump -t 'detroit.emp*' -T detroit.employee_log DATABASE > db.sql   # dump all tables whose names start with emp in the detroit schema, except for the table named employee_log
pg_dump -n 'east*gsm' -n 'west*gsm' -N '*test*' DATABASE > db.sql     # dump all schemas whose names start with east or west and end in gsm, excluding schemas whose names contain word test
pg_dump -n '(east|west)*gsm' -N '*test*' DATABASE > db.sql            # same as above, using regular expression notation to consolidate the switches
pg_dump -T 'ts_*' DATABASE > db.sql                                   # dump all database objects except for tables whose names begin with ts_
```

## see also

- [[psql]]
- [[mysqldump]]
- [[mongodump]]
- [postgresql.org/docs/9.0/libpq-envars](https://www.postgresql.org/docs/9.0/libpq-envars.html)
