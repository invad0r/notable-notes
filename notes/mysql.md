---
tags: [database]
title: mysql
created: '2019-07-30T06:19:49.179Z'
modified: '2020-03-26T13:49:49.207Z'
---

# mysql

> mysql cli tool

## install
`yum install mysql`

## usage
```sql
\g        -- go  Send command to mysql server. 
\G        -- ego Send command to mysql server, display result vertically.

-- info
select user,host from mysql.user;				-- list all users and privileges
select User from mysql.user;						-- list users
select USER(),CURRENT_USER();						-- current logged in user
desc config;														-- table info

-- show
SHOW processlist;												-- list processes
SHOW grants for 'root'@'%';							-- privilegs of specific user
SHOW databases;
SHOW engines;
SHOW TABLE STATUS;											-- lists egnine, version, index-length, ...
SHOW TABLES;
SHOW tables from foo;
SHOW FULL TABLES												-- show additional Views
SHOW TABLES LIKE 'p%';
SHOW TABLES LIKE '%es';
SHOW TABLES WHERE expression;
SHOW FULL TABLES WHERE table_type = 'VIEW';
SHOW VARIABLES LIKE "%version%";			-- get MySQL Version
SHOW VARIABLES LIKE "character_set_database";

-- search tablename in all databases
SELECT table_name, table_schema AS dbname FROM INFORMATION_SCHEMA.TABLES;
SELECT table_name, table_schema AS dbname FROM information_schema.tables where table_name = 'bewo_namen';

-- database size
SELECT table_schema "Data Base Name", sum( data_length + index_length) / 1024 / 1024 "Data Base Size in MB" 
FROM information_schema.TABLES 
GROUP BY table_schema ;

-- create databaes & user
CREATE DATABASE `someDB` CHARACTER SET utf8 COLLATE utf8_bin;
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
-- GRANT ALL PRIVILEGES ON `someDB`.* TO "someDB-user"@"localhost";
-- GRANT ALL PRIVILEGES ON `someDB`.* TO "someDB-user"@"localhost" IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON `someDB`.* TO "someDB-user"@"192.168.1.%";
FLUSH PRIVILEGES;
exit

CREATE DATABASE `database_name` CHARACTER SET utf8 COLLATE utf8_bin;
CREATE USER 'urlshortner'@'localhost' IDENTIFIED BY 'avg-_Duk3VG3BfRIRrsb';
GRANT ALL PRIVILEGES ON `urlshortnerdb`.* TO 'urlshortner'@'%' IDENTIFIED BY 'avg-_Duk3VG3BfRIRrsb';;
FLUSH PRIVILEGES;


-- privileges
GRANT SELECT,INSERT,UPDATE,DELETE ON `db`.* TO 'user'@'host';
FLUSH 
REVOKE all privileges on *.* FROM 'user'@'host';
show grants for 'urlshortner';
show grants for 'urlshortner'@'localhost';

-- COLLATE
utf8_unicode_ci
utf8_general_ci				-- applies Unicode normalization using language-specific rules and compares strings case-insensitively
utf8_general_cs				-- does the same, but compares strings case-sensitively
utf8_bin					    -- Compares strings by the binary value of each character in the string

ALTER DATABASE bitbucket CHARACTER SET utf8 COLLATE utf8_bin;
drop database bitbucket;


-- global variables
SHOW variables;
SET GLOBAL general_log = 'OFF';
SELECT status,COUNT(*) as count FROM table GROUP BY status ORDER BY count DESC;

-- transactions
START TRANSACTION;
SELECT * FROM nicetable WHERE somthing=1;
UPDATE nicetable SET nicefield='VALUE' WHERE somthing=1;
SELECT * FROM nicetable WHERE somthing=1; #check
COMMIT;
ROLLBACK;   -- or if you want to reset changes


INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...); 
```

## see also
- [[mongo]]
- [[psql]]
- [[sqlite]]
- [mysql-find-a-table-in-all-database - stackoverflow](http://stackoverflow.com/a/3756768)
- [how-to-create-a-new-user-and-grant-permissions - digitalocean.com](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql)
- [connecting-bitbucket-server-to-mysql](https://confluence.atlassian.com/bitbucketserver/connecting-bitbucket-server-to-mysql-776640382.html)
- [why-the-g-in-select-from-table-name-g](https://stackoverflow.com/a/40030346/2087704)
- [How to calculate the MySQL database size – Mkyong.com](http://www.mkyong.com/mysql/how-to-calculate-the-mysql-database-size/)
