---
tags: [kafka]
title: kafka
created: '2019-07-30T06:19:49.147Z'
modified: '2019-08-18T14:53:45.272Z'
---

# kafka

```sh
unset KAFKA_OPTS    # had to be set in certain contaier ?!
```
## list topics
```sh
kafka-topics.sh --zookeeper zookeeper:2181 --list


tree /kafka     # on fs

kafka
├── kafka-logs-2b982f8483a7
│   ├── cleaner-offset-checkpoint
│   ├── de.story-0
│   │   ├── 00000000000001296086.index
..
    
```
```sh    
kafka-topics.sh --zookeeper zookeeper:2181 --list
 
kafka-topics.sh --zookeeper zookeeper:2181 --describe --topic de.story
 
kafka-topics.sh --zookeeper zookeeper:2181 --create --topic foo.bar \
  --partitions 1 --replication-factor 1
```

### produce messages
```sh    
kafka-console-producer --broker-list kafka.service.ddev.domain.net:9094 --topic test

kafka-console-producer.sh --broker-list localhost:9092 --topic foo.bar
>hello
>what up
>^C
```

### consume messages
```sh    
kafka-console-consumer --bootstrap-server kafka.service.ddev.domain.net:9094 --topic test

kafka-console-consumer.sh --bootstrap-server localhost --topic foo.bar --from-beginning
```

### topic size
```sh    
kafka-run-class.sh kafka.tools.GetOffsetShell --broker-list localhost:9092 \
  --topic de.story --time -1 --offsets 1
```


### get offset
```sh    
kafka-run-class.sh kafka.tools.GetOffsetShell --broker-list localhost:9092 --topic foo.bar

kafka-console-consumer.sh --topic foo.bar --bootstrap-server localhost:9092 --partition 0 --offset 2
```

## server configuration
```sh
cat ./opt/kafka_2.12-2.1.1/config/server.properties | grep "^[^#;]"; 
```

### rest-proxy
```sh
curl -XPOST \
  http://foo.bar.baz:8082/topics/testTopic \
  -H 'Content-Type: application/vnd.kafka.json.v2+json' \
  -H 'cache-control: no-cache' \
  -d '{"records":[{"value":{"foo":"bar"}}]}'

curl -XGET http://foo.bar.baz:8082/topics

curl -XGET http://foo.bar.baz:8082/topics/testTopic

curl -s -XGET http://foo.bar.baz:8082/topics/testTopic/partitions |jq
```
