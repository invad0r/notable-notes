---
title: 12 factor app
created: '2022-02-15T10:15:31.700Z'
modified: '2022-04-04T13:17:34.056Z'
---

# 12 factor app

> methodology for building software-as-a-service apps

## 12 factors

## I. Codebase

> one codebase tracked in a vcs, many deploy

## II. Dependencies

> explicitly declare and isolat dependencies

?!

## III. Config

> store config in the environment

## IV. Backing Services

> treat backing services as attached resources

??

## V. Build, Release, Run

> strictly seperate build and run stages

what is a run stage ?

## VI. Processes

> execute app as one or more stateless processes

## VII. Port Binding

> export services via port binding

[[osi model]] [[tcp-ip model]]

## VIII. Concurrency

> scale out via process model

## IV. Disposability

> maximize robustness with fast startup and graceful shutdown

## X. Dev/prod parity

> keep development, staging and production as similar as possible

## XI. Logs

> treat logs as event streams

## XII. Admin Processes

> rund admin/management tasks as one-off processes

## see also

- [[devops]]
- [[unix socket]]
- [12factor.net](https://12factor.net/)
