---
title: pv
created: '2020-01-22T14:05:40.771Z'
modified: '2020-08-21T09:01:28.298Z'
---

# pv

> `pipe-viewr` - monitor the progress of data through a pipe 

## usage
```sh
pv file | nc -w 1 somewhere.com 3000                    # watch how quickly a file is transferred

cat file | pv -s 12345 | nc -w 1 somewhere.com 3000     # transferring a file from another process and passing the expected size to pv

# numeric output to feed into the dialog(1) program for a full-screen progress display:
( tar cf - . \
  | pv -n -s 'du -sb . | awk '{print $1}'' \
  | gzip -9 > out.tgz \
) 2>&1 | dialog --gauge 'Progress' 7 70

mysqldump -hxxx -uxxx -p dbname | pv -W > dump.sql

pv sqlfile.sql | mysql -uxxx -pxxxx dbname

mysqldump .. | pv --progress --size 100m > dumpfile.sql
mysqldump .. --hex-blob | pv --progress --size $SIZE_BYTES > dumpfile.sql


zcat "$INPUT_FILE" | pv -cN zcat | mysql --user=USER ..
zcat "$INPUT_FILE" | pv --progress --size $(gzip -l $INPUT_FILE | sed -n '2{p;q}' | awk '{print $2}') | mysql --user=USER ..

mysql_import() {
  zcat $2 | pv --progress --size `gzip -l %s | sed -n 2p | awk '{print $2}'` --name '  Importing.. ' | mysql -uuser -ppass $1
}


pv -tpreb /dev/zero | dd of=/dev/mapper/DEVICE bs=128M     # write zeros to device
```

## see
- [[mysqldump]]
- [[dialog]]
- [[tar]]
- [[nc]]
- [[awk]]
- [[dd]]
