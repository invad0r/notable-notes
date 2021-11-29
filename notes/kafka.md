---
title: kafka
created: '2019-07-30T06:19:49.147Z'
modified: '2021-10-31T14:56:47.545Z'
---

# kafka

> distributed event streaming platform

## usage
```sh
KAFKA_GC_LOG_OPTS
KAFKA_HEAP_OPTS                 # increase heapt memory
# KAFKA_HEAP_OPTS="-Xms2g -Xmx5g"
KAFKA_JVM_PERFORMANCE_OPTS
# KAFKA_JVM_PERFORMANCE_OPTS="-XX:MetaspaceSize=96m -XX:+UseG1GC -XX:MaxGCPauseMillis=20 -XX:InitiatingHeapOccupancyPercent=35 -XX:G1HeapRegionSize=16M -XX:MinMetaspaceFreeRatio=50 -XX:MaxMetaspaceFreeRatio=80"
KAFKA_JMX_OPTS
# KAFKA_JMX_OPTS="-Dcom.sun.management.jmxremote -Dcom.sun.management.jmxremote.port=12346 -Dcom.sun.management.jmxremote.rmi.port=12346 -Dcom.sun.management.jmxremote.local.only=false -Dcom.sun.management.jmxremote.authenticate=false -Dcom.sun.management.jmxremote.ssl=false"
KAFKA_LOG4J_OPTS
KAFKA_OPTS                      # unset if deployed with -javaagent
# KAFKA_OPTS=-javaagent:/jmx_prometheus_javaagent-0.12.0.jar=1234:/kafka-2_0_0.yml

./opt/kafka_2.12-2.1.1/config/server.properties  # server configuration

# kafka-acl
kafka-acls --authorizer-properties zookeeper.connect=ZOOKEEPER:2181 \
  --add --allow-principal User:CN=$FQDN \
  --operation All --topic '*' --group '*' --transactional-id '*'

kafka-acls --authorizer-properties zookeeper.connect=ZOOKEEPER:2181 --list


# kafka-topics
kafka-topics --zookeeper ZOOKEEPER:2181 --list     # list topics   see also`tree /kafka`

kafka-topics --zookeeper ZOOKEEPER:2181 --describe 

kafka-topics --zookeeper ZOOKEEPER:2181 --describe --topic de.story
 
kafka-topics --zookeeper ZOOKEEPER:2181 --create --topic TOPIC --partitions 1 --replication-factor 1


# kafka-console-producer
kafka-console-producer --broker-list BROKER:9094 --topic TOPIC          # produce messages

kafka-console-producer --producer.config CONF --broker-list BROKER:9092 --topic TOPIC    # then start typing


# kafka-console-consumer
kafka-run-class kafka.tools.ConsoleConsumer "$@"

kafka-console-consumer --bootstrap-server BROKER:9092 --topic TOPIC --from-beginning           # consume messages

kafka-console-consumer --bootstrap-server BROKER:9092 --topic TOPIC --partition 0 --offset 2   # get offset

kafka-console-consumer --consumer.config CONF --bootstrap-server BROKER:9092 --topic TOPIC  --from-beginning

# get offset information
kafka-console-consumer --consumer.config CONF --bootstrap-server BROKER:9094 --topic __consumer_offsets \
  --formatter "kafka.coordinator.group.GroupMetadataManager\$OffsetsMessageFormatter"


# kafka-delete-records
kafka-delete-records --command-config CONF --bootstrap-server BROKER:9092 --offset-json-file offset-json.json
#  { "partitions": [ {"topic": "customerEvents", "partition": 0, "offset": 609} ], "version": 1 }


# kafka-consumer-groups
kafka-run-class kafka.admin.ConsumerGroupCommand

kafka-consumer-groups --command-config CONF --bootstrap-server BROKER:9092 --list     # list consumer groups

kafka-consumer-groups --command-config CONF --bootstrap-server BROKER:9092 --describe --group GROUP

kafka-consumer-groups --consumer.config CONF --bootstrap-server BROKER:9092 \
  --group GROUP --reset-offsets --to-earliest --all-topics --execute


# kafka-run-class
kafka-run-class kafka.tools.GetOffsetShell --command-config CONF --broker-list BROKER:9092 --topic TOPIC   # get offset

kafka-run-class kafka.tools.GetOffsetShell --broker-list BROKER:9092 --topic de.story --time -1 --offsets 1      # topic size


# kafka-broker-api-versions
kafka-broker-api-versions --bootstrap-server BROKER:9092 --command-config CONF
```

## see also
- [[java]]
- [[kafka rest-proxy api]]
- [[kafka schema-registry api]]
- [[zookeeper-shell]]
