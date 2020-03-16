---
tags: [Notebooks]
title: devops
created: '2019-07-30T06:19:49.034Z'
modified: '2020-03-13T13:52:37.068Z'
---

# devops

### aproach to fixing 3 Problems through
- culture
- automation
- measurement and sharing

### Fundamental Assumptions of DevOps

Achieving:
1. Frequent
2. Reliable deployments and
3. stable production environment

---

# devopscon berlin 2018

## 1. keynote charity [09:15-09:45]

* known uknowns
* observability (=> control theory term) driven development
  * quickly reliably track down new Problem
* can't predict top 10-20% of Problems

### best practices
- events not metrics
- dashboards can be misleading (dashborad = artefact of past failure)
- sampling not aggregation
- instrumentation
- events tell storeis (high cardinalities e.g. (high) UUID vs (low) gender )


## 2. k8s patterns [10:00-11:00]

- not imperative but declarative
- resource oriented
- pattern -> repeatable solution
- structure: Problem-Name then solution


- predictable demands
  - dependencies:
    - runtime (persist volumes)
    - resource profiles (CPU and Net)
  - QOS-Classes (requests & Limits)
    - Best effort no r or L
    - burstable   r < L
    - Guaranteed  r == L
- declarative deplyoment
  - deployment object holds (pods, replicaset, deploy-config)
- structural pattersn
  - "initalizer" how to init container ?
  - "sidecar" external functionality ? without changin container/pod
  - "ambassador"/"Proxy" decouple acces to outside world ?
- config patterns
  - configure different environments
  - "EnvVars" 12 Factor Apps (-) only during startup
  - "config-resource"
  - "config template"
  - "immutable config"
    - everything into container
    - "flexvol-docker/not k8s" shared volumes

[GitHub - ro14nd-talks/kubernetes-patterns: Kubernetes Patterns - Presentation around https://leanpub.com/k8spatterns/](https://github.com/ro14nd-talks/kubernetes-patterns)

## 3. K8s 101
- "broken by design" => "memorize IP ? you crazy ?"
- all containers in pod have same loopback device
- all containers in pod have same IP !!!

## 4. keynote
- gVisor lightweight Hypervisor
- multicloud with k8s

## 5. sustain devops cutlure

- devops is a people problems
- intentions is to support decision making
- theory of constraints
- "walk in my shoes"
  - watch others do their job
  - solve specific problem
- cultural mindset
  - people will adapt
  - clear expectation and boundaries
- invocation vs predictability
  - be clear about time-slots and coutcome
- growing people like plants
  - environment
  - balanced fertilizer
- "society of emergency docktors" => short attention spanc
- appreciate solved problems not just corssing of checklist !
  - e.g. dba-queryy -> stupid dev, bt 30% load reduced !
- __Autonomy FOLLOWS alignment__ <= company goal !!
- judgement in retrospective is easy
- devops -> collaboration -> look outside your box -> empathy

## 6. infra as cod - buildpipelines

## 7. monitoring the uknown
- statsd
- openTSDB

```
Root Cause Analysis
method of problem solving used for identifying the root-cause of faults or problems

a factor is considered a root-cause if removal fromt he problem-fault-sequence prevents the final undesirable event from reocouring
```

## 8. keynote

"consistency bias"

devops is a revolutionary adaptation to adapt to exponensial change

maxim: Adapt or die

"lean thinking" silos

be disruptive or be disrupted
frequency of innovation

| F. Winslow Tylor | W.Edward Deming |
|--|--|
| Efficienty Movement | Lean Movement |
| Power & Fear | Japan after WWII |

"change for change's sake is dangerous" if not "anchored-change"

control vs adaptation

hirarchy vs decentralization

