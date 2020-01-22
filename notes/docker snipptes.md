---
deleted: true
tags: [container, container/docker]
title: docker snipptes
created: '2019-07-30T06:19:49.041Z'
modified: '2020-01-21T10:03:56.842Z'
---

# docker snipptes

### prompts
```sh
docker exec -it --env 'PS1=[consul]\w \$ ' consul ash   # set prompt 

docker exec -it --env 'PS1=['$ENV_KEY'] \s-\v\$ ' nexus_nexus_1 bash
```

### format
```sh
docker ps -a --no-trunc --filter name=^/foo$            # list container who's name is "/foo"

docker ps --format "table {{.ID}}\t{{.Image}}\t{{.Names}}" | awk '{ if( $2 !~ /^docker-registry/) print}'

docker info --format="{{json .LiveRestoreEnabled}}"
```

### manage docker inside of docker
```sh
docker run -it -v /var/run/docker.sock:/var/run/docker.sock ubuntu:latest \
  sh -c "apt-get update ; apt-get install docker.io -y ; bash"

docker run --rm httpd:2.4-alpine htpasswd -nbB admin PASSWORD | cut -d ":" -f 2    # generate password

```

### debugging
```sh
docker logs nginx 2>&1 | grep "127."    # grepping logs with 2>&1

docker events

docker inspect 0                        # low level information about container

docker inspect 16e3103698c2 | jq '.[] | .Config .Image'

docker inspect --format '{{.State.Running}}' $CONTAINER_ID    # container running

docker inspect --format '{{ index .Config.Labels "com.foo.bar" }}' foo   # index function: can lookup arbitrary strings in the map

```
### stats
```sh
docker stats $(docker inspect -f '{{.Name}}' $(docker ps -q) | cut -c 2-)

docker stats $(docker ps --format={{.Names}})
```

## swarm task-history
```sh
docker swarm update --task-history-limit=1

docker info --format "{{json .Swarm}}" | jq '.Cluster.Spec.Orchestration.TaskHistoryRetentionLimit'
```

## failed to deactivate service binding for container srv

```sh
network_name="ingress"
for endpoint_map in $(docker network inspect -f '{{range $container_id, $container_def := .Containers}} {{$container_id}}^{{index $container_def "Name"}} {{end}}' $network_name); do
  container_id=$(echo $endpoint_map | cut -d ^ -f1)
  container_name=$(echo $endpoint_map | cut -d ^ -f2)

  if [ $container_id != "ingress-sbox" ]; then
    docker inspect --format "{{.State.Status}}" $container_id &>/dev/null
    if [ $? -ne 0 ]; then
      echo "Removing $container_name"
      echo docker network disconnect -f $network_name $container_name
    else
      echo "Letting $container_name stay"
    fi
  fi
done
```

## see also
- [[awk]]
- [linux - How to clear Docker task history - Stack Overflow](https://stackoverflow.com/questions/42364695/how-to-clear-docker-task-history#)
- [Starting container failed: Address already in use · GitHub](https://github.com/moby/moby/issues/31698#issuecomment-320294893)

