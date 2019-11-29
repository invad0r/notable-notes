---
tags: [erlang]
title: rabbitmqctl
created: '2019-07-30T06:19:49.223Z'
modified: '2019-11-29T10:45:28.608Z'
---

# rabbitmqctl

> RabbitMQ is an open-source message-broker software that originally implemented the Advanced Message Queuing Protocol and has since been extended with a plug-in architecture to support Streaming Text Oriented Messaging Protocol, Message Queuing Telemetry Transport, and other protocols

## usage
```sh
rabbitmqctl status

rabbitmqctl environment

rabbitmqctl eval 'application:get_all_env(kernel).' 
```

## see also
- [[kafka]]
