---
title: kafka
created: '2019-07-30T06:19:49.147Z'
modified: '2020-06-18T09:49:53.265Z'
---

# kafka

## usage
```sh
unset KAFKA_OPTS    # unset if deployed with -javaagent

cat ./opt/kafka_2.12-2.1.1/config/server.properties | grep "^[^#;]";  # server configuration
```

## kafka-acl
```sh
kafka-acls --authorizer-properties zookeeper.connect=ZOOKEEPER:2181 \
  --add --allow-principal User:CN=$FQDN \
  --operation All --topic '*' --group '*' --transactional-id '*'

kafka-acls --authorizer-properties zookeeper.connect=ZOOKEEPER:2181 --list
```

## kafka-topics
```sh
kafka-topics --zookeeper ZOOKEEPER:2181 --list     # list topics   see also`tree /kafka`

kafka-topics --zookeeper ZOOKEEPER:2181 --describe 

kafka-topics --zookeeper ZOOKEEPER:2181 --describe --topic de.story
 
kafka-topics --zookeeper ZOOKEEPER:2181 --create --topic TOPIC --partitions 1 --replication-factor 1
```

## kafka-console-producer
```sh    
kafka-console-producer --broker-list BROKER:9094 --topic TOPIC          # produce messages

kafka-console-producer --producer.config CONF --broker-list BROKER:9092 --topic TOPIC    # then start typing
```

## kafka-console-consumer
```sh
kafka-run-class kafka.tools.ConsoleConsumer "$@"

kafka-console-consumer --bootstrap-server BROKER:9092 --topic TOPIC --from-beginning           # consume messages

kafka-console-consumer --bootstrap-server BROKER:9092 --topic TOPIC --partition 0 --offset 2   # get offset

kafka-console-consumer --consumer.config CONF --bootstrap-server BROKER:9092 --topic TOPIC  --from-beginning

# get offset information
kafka-console-consumer --consumer.config CONF --bootstrap-server BROKER:9094 --topic __consumer_offsets \
  --formatter "kafka.coordinator.group.GroupMetadataManager\$OffsetsMessageFormatter"
```

## kafka-delete-records
```sh
kafka-delete-records --command-config CONF --bootstrap-server BROKER:9092 --offset-json-file offset-json.json
#  { "partitions": [ {"topic": "customerEvents", "partition": 0, "offset": 609} ], "version": 1 }
```

## kafka-consumer-groups
```sh
kafka-run-class kafka.admin.ConsumerGroupCommand

kafka-consumer-groups --command-config CONF --bootstrap-server BROKER:9092 --list     # list consumer groups

kafka-consumer-groups --command-config CONF --bootstrap-server BROKER:9092 --describe --group GROUP

kafka-consumer-groups --consumer.config CONF --bootstrap-server BROKER:9092 \
  --group GROUP --reset-offsets --to-earliest --all-topics --execute
```

## kafka-run-class
```sh    
kafka-run-class kafka.tools.GetOffsetShell --command-config CONF --broker-list BROKER:9092 --topic TOPIC   # get offset

kafka-run-class kafka.tools.GetOffsetShell --broker-list BROKER:9092 --topic de.story --time -1 --offsets 1      # topic size
```

## kafka-broker-api-versions
```sh
kafka-broker-api-versions --bootstrap-server BROKER:9092 --command-config CONF
```

## see also
- [[kafka rest-proxy api]]
- [[kafka schema-registry api]]
- [[zookeeper-shell]]
