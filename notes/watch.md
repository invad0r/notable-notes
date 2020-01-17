---
tags: [linux]
title: watch
created: '2019-07-30T06:19:49.265Z'
modified: '2020-01-16T20:27:46.908Z'
---

# watch
> execute a program periodically, showing output fullscreen

## usage
```sh
watch -d "ps -ef | awk -F' ' '{print \$2}'"   # use double quotes and escape $
  # -n .5  --interval

watch -d 'docker service ps --filter desired-state=running --format "{{.Node}} {{.Name}}" $(docker service ls --filter mode=replicated -q)'

watch 'for pid in `jps` ; do echo -n "$pid " && ps huH p $pid | wc -l ; done'     # poor man java monitoring
```

## watch alternative
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
- [[consul]]
- [Using the watch command with an argument that contains quotes - Super User](https://superuser.com/a/276706)
- [[bash while]]
- [[bash printf]]
