---
title: pv
created: '2020-01-22T14:05:40.771Z'
modified: '2020-01-22T14:11:06.445Z'
---

# pv

>  monitor the progress of data through a pipe

## usage

```sh
pv file | nc -w 1 somewhere.com 3000                    # watch how quickly a file is transferred

cat file | pv -s 12345 | nc -w 1 somewhere.com 3000     # transferring a file from another process and passing the expected size to pv

# numeric output to feed into the dialog(1) program for a full-screen progress display:
( tar cf - . \
  | pv -n -s 'du -sb . | awk '{print $1}'' \
  | gzip -9 > out.tgz \
) 2>&1 | dialog --gauge 'Progress' 7 70
```

## see
- [[dialog]]
- [[tar]]
- [[nc]]
- [[awk]]
