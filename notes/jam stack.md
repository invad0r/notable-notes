---
title: jam stack
created: '2022-04-08T10:29:14.554Z'
modified: '2022-04-08T21:03:39.322Z'
---

# jam stack

> `javascript api markup` - community collection of best practices and workflows that result in high-speed websites

## jam stack sites are

- globally distributed and resilient to heavy traffic
- centred around developer friendly git-based workflow
- designed modularily, consuming other services via apis
- prebuild and optimized before being served



##

```
   server-side            client-side            static-site-generation
    
  /product/widget        /product/widget         /product/widget

  ┌───────────┐          ┌───────────┐           ┌───────────┐
  │  client   │          │  client   │           │  client   │
  └─────▲─────┘          └▲────────▲─┘           └─────▲─────┘
        │                 │        │                   │
Rendered Response         │        │                   │
        │                 │        │                   │
  ┌─────┴──────┐     Blank Page    │               ┌───┴────┐
  │ Web Server │          +        │               │   S3   │
  └─────▲──────┘     JavaScript    │               └───▲────┘
        │                 │        │                   │
      data        ┌───────┴────┐  data          ┌──────┴───────┐
        │         │ Web Server │   │            │ Build Server │
  ┌─────┴──────┐  └────────────┘   │            └──────▲───────┘
  │ API Server │                   │                   │
  └────────────┘           ┌───────┴────┐        ┌─────▼──────┐
                           │ API Server │        │ API Server │
                           └────────────┘        └────────────┘

```


platforms: [[hugo]], [[jekyll]], [[gatsby]]
services: netlify, now.sh, zeit
apis: aws-amplify, firebase



## see also

- [[micro frontend]]
- [[edge side include]]
