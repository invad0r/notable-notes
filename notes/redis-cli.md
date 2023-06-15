---
tags: [cloud, linux]
title: redis-cli
created: '2022-10-05T12:58:56.515Z'
modified: '2023-05-24T08:40:38.318Z'
---

# redis-cli

## install

```sh
apt-get install redis-tools
```

## usage

```sh
redis-cli --scan --pattern '*-11*'

redis-cli --latency
```

## console

```
127.0.0.1:6379> SET mykey "Hello\nWorld"
OK
127.0.0.1:6379> GET mykey
Hello
World
```

```sh
nc -v --ssl HOST 6380
```

## see also

- [[nc]]
- [[zookeeper-shell]]
- [redis.io/docs/manual/cli](https://redis.io/docs/manual/cli/)
