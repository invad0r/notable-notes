---
tags: [bash, bash/keyword]
title: bash until
created: '2019-07-30T06:19:49.023Z'
modified: '2019-08-18T19:34:02.139Z'
---

# bash until

```sh
until condition; do
  statements
done
```

### wait for database to come up

```sh
until nc -z -v -w30 "$DB_HOST" "$DB_PORT"; do
  echo "Waiting for database connection..."
  sleep 2
done
```

see also: [[nc]]
