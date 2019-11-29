---
title: kafka
created: '2019-07-30T06:19:49.147Z'
modified: '2019-11-29T10:42:21.193Z'
---

# kafka

## config
```sh
unset KAFKA_OPTS    # unset if deployed with -javaagent

cat ./opt/kafka_2.12-2.1.1/config/server.properties | grep "^[^#;]";  # server configuration
```

## kafka-topics
```sh
kafka-topics --zookeeper zookeeper-1:2181 --list     # list topics   see also`tree /kafka`

kafka-topics --zookeeper zookeeper-2:2181 --describe 

kafka-topics --zookeeper zookeeper-1:2181 --describe --topic de.story
 
kafka-topics --zookeeper zookeeper-1:2181 --create --topic foo.bar --partitions 1 --replication-factor 1
```

## kafka-console-producer
```sh    
kafka-console-producer --broker-list kafka-1:9094 --topic test          # produce messages

kafka-console-producer --broker-list kafka-1:9092 --topic foo.bar    # then start typing
```

## kafka-console-consumer
> `kafka-run-class kafka.tools.ConsoleConsumer "$@"`
```sh
kafka-console-consumer --bootstrap-server kafka-1:9094 --topic test   # consume messages

kafka-console-consumer --bootstrap-server kafka-1:9092 --topic foo.bar --from-beginning

kafka-console-consumer --bootstrap-server kafka-1:9092 --topic foo.bar --partition 0 --offset 2  # get offset

kafka-console-consumer --consumer.config ssl.conf --bootstrap-server kafka-1:9092 --topic customerEvents --from-beginning
```

## kafka-delete-records
```sh
kafka-delete-records --command-config ssl.conf --bootstrap-server kafka-1:9092 --offset-json-file offset-json.json
```
```json
{
  "partitions": [ {"topic": "customerEvents", "partition": 0, "offset": 609} ],
  "version": 1
}
```

## kafka-consumer-groups
```sh
kafka-consumer-groups --command-config ssl.conf --bootstrap-server kafka-1:9092 --list     # list consumer groups

kafka-consumer-groups --command-config ssl.conf --bootstrap-server kafka-1:9092 -describe -group my-stream-processing-application

kafka-consumer-groups --consumer.config ssl.conf --bootstrap-server kafka-host:9092 --group my-group --reset-offsets --to-earliest --all-topics --execute
```

## kafka-run-class
```sh    
kafka-run-class kafka.tools.GetOffsetShell --command-config ssl.conf --broker-list kafka-1:9092 --topic foo.bar                          # get offset

kafka-run-class kafka.tools.GetOffsetShell --broker-list kafka-1:9092 --topic de.story --time -1 --offsets 1   # topic size
```

## kafka-broker-api-versions
```sh
kafka-broker-api-versions --bootstrap-server kafka-2:9092 --command-config ssl.conf
```

## see also
- [[kafka rest-proxy]]
- [[kafka schema-registry]]
- [[zookeeper]]
- [[rabbitmqctl]]
