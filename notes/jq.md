---
tags: [json, linux]
title: jq
created: '2019-07-30T06:19:49.141Z'
modified: '2019-10-23T14:21:39.243Z'
---

# jq

> Command-line JSON processor - transform JSON in various ways, by selecting, iterating, reducing and otherwise mangling JSON documents

## flags
```sh
--raw-output, -r      # output no quotes

--unbuffered          # if you're piping a slow data source into jq and piping jq's output elsewhere

--null-input, -n      # Don't read any input at all! useful when using jq as a simple calculator or to construct JSON data from scratch

--sort-keys, -S       # Output the fields of each object with the keys in sorted order
                      # diff <(jq -S . fileA.json) <(jq -S . fileA.json)
```

## `tojson` `fromjson`
```sh
echo '[1, "foo", ["foo"]]' | jq '. | tostring'

echo '[1, "foo", ["foo"]]' | jq '. | tojson'

echo '"[1,\"foo\",[\"foo\"]]"' | jq '. | fromjson'
```

## string interpolation
```sh
STDOUT | jq '.[]| "\(.id) \(.name)"'  # print in one line

jq -n -r '["abc","def"] | "\(.[0]) \(.[1])"'
```

```sh
STDOUT | jq -r '.auths | keys[]'   # get only keys from auths{} object
```
## select
- get a object based on object's value
```sh
jq '.VirtualMachines[].Config.Hardware.Device[] | select(.Key== 2000) | .CapacityInBytes'
```

### filter values
```sh
STDOUT | jq --unbuffered 'map(del(.database, .id, .isDefault, .jsonData, .orgId, .password, .typeLogoUrl, .user))' # removes from .[], ..map for array 

STDOUT | jq --unbuffered 'map({access, basicAuth, name, type, url})'   # keeps whitelisted from .[]

STDOUT | jq 'map(.price) | add'         #  will take an array of JSON objects as input and return the sum of their "price" fields
```

```sh
echo '{"hello": "world"}' | jq --arg foo bar '. + {foo: $foo}'      # add field: {  "hello": "world", "foo": "bar"  }

echo '{"hello": "world"}' | jq --arg foo bar '. + {hello: $foo}'    # override field value: { "hello": "bar" }

echo '{"hello": "world"}' | jq --arg foo bar '. + {hello: ("not" + $foo)}'    # concat and add: { "hello": "world", "foo": "notbar" }
```

### print in same line
```sh
docker exec -t consul consul watch -type=service -service=swarm-a \
  | jq -r '.[] | [.Node.Node, .Service.Service] | @tsv'    # input must be an array, and it is rendered as TSV (tab-separated values).
```

### get value of dynamic object names
```sh
STDOUT | jq -r '.servers  | keys[] as $k | "\(.[$k] | .url)"'
  
# { "traefik-metrics-192-csHt9CK1Pq5ATmZ-i-8km0dPkoU": { "url": "http://10.32.23.150:7070", "weight": 1 },
#  "traefik-metrics-193-zHtiw3Y4-N-RYUIP7DxczqBU3ZE": { "url": "http://10.32.23.151:7070", "weight": 1 },
#
# results:
# http://10.32.23.150:7070
# http://10.32.23.151:7070
```

## see also
- [[yq]]
- [[govc vm]]
- [jq print key and value for all in sub-object - Unix & Linux Stack Exchange](https://unix.stackexchange.com/a/406425)
- [Printing multiple values on the same line - Stack Overflow](https://stackoverflow.com/a/46131963)
