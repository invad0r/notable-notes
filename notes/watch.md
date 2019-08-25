---
tags: [linux]
title: watch
created: '2019-07-30T06:19:49.265Z'
modified: '2019-08-20T07:20:01.244Z'
---

# watch


```sh
watch -d "ps -ef | awk -F' ' '{print \$2}'"   # use double quotes and escape $
  # -n .5  --interval
```
[bash - Using the watch command with an argument that contains quotes - Super User](https://superuser.com/a/276706)

```sh
watch -d 'docker service ps --filter desired-state=running --format "{{.Node}} {{.Name}}" $(docker service ls --filter mode=replicated -q) | sort | column -t'
```

### poor man java monitoring
```sh
watch 'for pid in `jps` ; do echo -n "$pid " && ps huH p $pid | wc -l ; done'   
```

### watch-alternative using while
```sh
while sleep 5; do   # every 5 seconds
  printf "\033c";   # clear screen
  for node in $(consul members | awk '{ if($1 ~ "swarm" && $3 == "alive"){ print $1} }'); do 
    echo "$node"; consul catalog services -node $node | grep "cadvisor\|export"; 
    echo; 
  done
done
```
