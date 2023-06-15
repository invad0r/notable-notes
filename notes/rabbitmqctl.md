---
tags: [erlang]
title: rabbitmqctl
created: '2019-07-30T06:19:49.223Z'
modified: '2023-05-24T14:42:06.126Z'
---

# rabbitmqctl

> message-broker, originally implemented `Advanced Message Queuing Protocol` 
> has since been extended with a plug-in architecture to support
> `Streaming Text Oriented Messaging Protocol`, `Message Queuing Telemetry Transport` and other protocols

## usage

```sh
rabbitmqctl status

rabbitmqctl environment

rabbitmqctl eval 'application:get_all_env(kernel).' 
```

## see also

- [[erlang]]
- [[aws]] `sns`/`sqs`
- [[kafka]]
