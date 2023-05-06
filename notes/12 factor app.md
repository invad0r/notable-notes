---
tags: [Notebooks]
title: 12 factor app
created: '2022-02-15T10:15:31.700Z'
modified: '2023-04-25T08:26:28.980Z'
---

# 12 factor app

> methodology for building software-as-a-service apps

## 12 factors

- was developed by heroku
- is as set of best practices aswell as a mindset

## I. Codebase

> one codebase tracked in a vcs, many deploy

- multiple developers push to single source base via git
- services that comprise one app should each have a seperate codebase

## II. Dependencies

> explicitly declare and isolate dependencies

- a twelve factor app never relies on implicit existence of system wite packages
- declare dependecies explicitly e.g. `flask==2.0.0` in `requirements.txt`
- isolate environment using virtual environments like [[virtualenv]] or [[docker]]

## III. Config

> store config in the environment

- store config values in environment variables
- seperate set of environment variable per stage

## IV. Backing Services

> treat backing services as attached resources

- attached resoruce meaning it should be no problem switching to a differen redis instance

## V. Build, Release, Run

> strictly seperate build and run stages

- strict seperation between `build`, `release`and `run` stages
1. build: generate executable -> e.g `docker build`
2. release: executable + config = `release object`, should have release id, tag
3. run:

## VI. Processes

> execute app as one or more stateless processes

- processes are stateless and share-nothing
- sticky sessions are a violation of twelve-factor and should never be used or relied upon if data is stored locally on the process (data loss!)
- use `IV. Backing Services` like redis or a db to share data between processes

## VII. Port Binding

> export services via port binding

- twelve-factor app is completely self-contained and does not rely on specific server to function
- [[osi model]] [[tcp-ip model]]

## VIII. Concurrency

> scale out via process model

- to use horizontal scaling the app must be independant and stateless
- processes are first class citizen -> app should scale horizontally not vertically -> `VI. Processes`

## IV. Disposability

> maximize robustness with fast startup and graceful shutdown

- app's processes are disposable and should be started or stopped at a moments notice
- app's processes should shutdown gracefully when receiving a `SIGTERM` [[signal]] from process manager, avoiding unexpected dataloss

## X. Dev/prod parity

> keep development, staging and production as similar as possible

- designed for Continous Deployment by keepking gap between dev and prod small
- developer resists the urge to use different backing services betweetn dev and prod

## XI. Logs

> treat logs as event streams

- twelve factor app never concerns itself with routing or storage of it output stream
- store logs in centralized location in structured format
- don't store logs in local fs -> `IV. Disposability`
- ouput logs to `STDOUT` which can be transported by agent (fluentd) to centralized logging system (ELK-Stack, Splunk)

## XII. Admin Processes

> rund admin/management tasks as one-off processes

- administrative tasks should be kept seperate from app process
- database migration or restart should be run as seperate process e.g. start coontainer in parallel to run migration

## see also

- [[devops]]
- [[unix socket]]
- [12factor.net](https://12factor.net/)
- [[iac]]
