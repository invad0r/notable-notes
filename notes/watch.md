---
tags: [linux]
title: watch
created: '2019-07-30T06:19:49.265Z'
modified: '2023-03-22T08:07:02.520Z'
---

# watch

> execute a program periodically, showing output fullscreen

## env

```sh
WATCH_INTERVAL            # persistently set a non-default interval
```

## flags

```sh
-n, --interval SECONDS    # update interval,  will not allow quicker than 0.1 second interval, in which the smaller values are converted 
```

## usage

```sh
watch -d "ps -ef | awk -F' ' '{print \$2}'"   # use double quotes and escape $

watch -d 'docker service ps --filter desired-state=running --format "{{.Node}} {{.Name}}" $(docker service ls --filter mode=replicated -q)'

watch 'for pid in `jps` ; do echo -n "$pid " && ps huH p $pid | wc -l ; done'     # poor man java monitoring
```

### watch alternative

```sh
while sleep 5; do   # every 5 seconds
  printf "\033c";   # clear screen
  for node in $(consul members | awk '{ if($1 ~ "swarm" && $3 == "alive"){ print $1} }'); do 
    echo "$node"; consul catalog services -node $node | grep "cadvisor\|export"; 
    echo; 
  done
done
```

## see also

- [[procps]]
- [[consul]]
- [[bash while]]
- [[bash printf]]
- [Using watch with an argument that contains quotes](https://superuser.com/a/276706)
