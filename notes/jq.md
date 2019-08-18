---
tags: [bash, cli, json]
title: jq
created: '2019-07-30T06:19:49.141Z'
modified: '2019-08-02T08:25:27.898Z'
---

# jq

```sh
  --raw-output / -r   # output no quotes

  --unbuffered        # if you're piping a slow data source into jq and piping jq's output elsewhere
```

```sh
cat .docker/config.json | jq -r '.auths | keys[]'   # get only keys from auths{} object
```


```sh
# Add field
echo '{"hello": "world"}' | jq --arg foo bar '. + {foo: $foo}'
# {
#   "hello": "world",
#   "foo": "bar"
# }


# Override field value
echo '{"hello": "world"}' | jq --arg foo bar '. + {hello: $foo}'
# {
#   "hello": "bar"
# }


# Concat and add
echo '{"hello": "world"}' | jq --arg foo bar '. + {hello: ("not" + $foo)}'
# {
#   "hello": "world",
#   "foo": "notbar"
# }
```

### filter values
```sh
# removes from .[], ..map for array 
| jq --unbuffered 'map(del(.database, .id, .isDefault, .jsonData, .orgId, .password, .typeLogoUrl, .user))'

# keeps whitelisted from .[]
| jq --unbuffered 'map({access, basicAuth, name, type, url})'
```

### pint in same line
```sh
docker exec -t consul consul watch -type=service -service=swarm-a \

  | jq -r '.[] | [.Node.Node, .Service.Service] | @tsv'    # input must be an array, and it is rendered as TSV (tab-separated values).

  | jq -r '.[] | "\(.Node.Node) \(.Service.Service)"'      # String interpolation
```
[json - Printing multiple values on the same line - Stack Overflow](https://stackoverflow.com/a/46131963)

### get value of dynamic object names
```sh
# {
#  "traefik-metrics-192-csHt9CK1Pq5ATmZ-i-8km0dPkoU": {
#    "url": "http://10.32.23.150:7070",
#    "weight": 1
#  },
#  "traefik-metrics-193-zHtiw3Y4-N-RYUIP7DxczqBU3ZE": {
#    "url": "http://10.32.23.151:7070",
#    "weight": 1
#  },
# ...

curl --silent --request GET --url http://swarm-a.service.ddev.domain.net:7070/api/providers/consul_catalog/backends/backend-traefik-metrics \
  | jq -r '.servers  | keys[] as $k | "\(.[$k] | .url)"'
  
# http://10.32.23.150:7070
# http://10.32.23.151:7070
# ..
```
[json - jq print key and value for all in sub-object - Unix & Linux Stack Exchange](https://unix.stackexchange.com/a/406425)


## compare
```sh
jq -S . fileA.json > fileA_fmt.json
jq -S . fileB.json > fileB_fmt.json

diff fileA_fmt.json fileB_fmt.json
```
