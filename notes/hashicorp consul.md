---
title: hashicorp consul
created: '2019-07-30T06:19:49.077Z'
modified: '2019-08-19T14:12:04.100Z'
---

# hashicorp consul

```sh
docker exec -it --env 'PS1=[consul]\w \$ ' consul ash

consul catalog nodes -service=swarm-a -detailed

consul watch -type=service -service=

consul watch -type=service -service=service

consul operator raft list-peers
```

## check consul catalog for services names to pop up
```sh
while sleep 5; do 
  printf "\033c";
  for node in $(consul members | awk '{ if($1 ~ "svs" && $3 == "alive"){ print $1} }'); do 
    echo "$node"; consul catalog services -node $node | grep "cadvisor\|export"; echo; 
  done
done

docker exec -it consul consul catalog nodes \
  | awk 'BEGIN{ NF=NF RS= OFS=+ }{ if ($3 ~ /^[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}/) { gsub(/^[[:space:]]+|[[:space:]]+$/,"",$1); print $1} }'

docker exec -it consul consul catalog nodes \
  | awk 'BEGIN{ ORS="\n" }{ if ($3 ~ /^[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}/) { print $1} }'

```


## web api
```sh
curl \
  --write-out "\n" \
  --request PUT \
  --data '{ "Datacenter": "dc1", "Node": "swarm-3", "Address": "10.32.23.208", "ServiceName": "swarm-b" }' \
  --url http://foo.bar.baz/v1/catalog/register

# /v1/catalog/services
# /v1/catalog/register
```
