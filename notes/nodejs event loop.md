---
tags: [javascript, node, Notebooks]
title: nodejs event loop
created: '2023-05-08T17:48:15.446Z'
modified: '2023-05-24T08:41:05.014Z'
---

# nodejs event loop

> allows node to perform non-blocking i/o operations, although js is single-threaded , by offloading operations to system kernel whenever possible


```sh
   ┌───────────────────────────┐
┌─>│ [ ]     timers            │<-- setTimeout(), setInteval()
│  └─────────────┬─────────────┘
│  ┌─────────────┴─────────────┐
│  │ [ ]     pending callbacks │
│  └─────────────┬─────────────┘
│  ┌─────────────┴─────────────┐
│  │ [ ]     idle, prepare     │
│  └─────────────┬─────────────┘      ┌───────────────┐
│  ┌─────────────┴─────────────┐      │   incoming:   │
│  │ [ ]     poll              │<─────┤  connections, │
│  └─────────────┬─────────────┘      │   data, etc.  │
│  ┌─────────────┴─────────────┐      └───────────────┘
│  │ [ ]     check             │
│  └─────────────┬─────────────┘
│  ┌─────────────┴─────────────┐
└──┤ [ ]     close callbacks   │
   └───────────────────────────┘

FIFO of callbacks
```

libuv -> c-lib implements node-event-loop + all async behavior

`unicorn velociraptor`

## see also

- [[node]]
- [nodejs.org/en/docs/guides/event-loop-timers-and-nexttick](https://nodejs.org/en/docs/guides/event-loop-timers-and-nexttick)
