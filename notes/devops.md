---
tags: [Notebooks]
title: devops
created: '2019-07-30T06:19:49.034Z'
modified: '2023-04-24T09:37:10.381Z'
---

# devops

> tries to solve a human problem: lack of communication and collaboration
> => profound culture shift (communication daily)

Cultur
Automation
Lean
Measurement
Sharing

CI: deploys per day => relative success; 10+ deploys per dai "allspaw"

> DevOps also characterized by operations staff making use of many of the same techniques as developers for their systems work

Agile (Biz + Dev) | <- | DevOps (Dev + Ops)
--|--|--
Agile Software Development | | Agile Software Delivery and Operations
Agile Values (manifesto) | | DevOps Values (people over process over tools)
Agile Principles [12] | | DevOps Principles (CAMS, Infra-as-Code)
Agile Methods (xp, scrum) | | DevOps Methods (Kanba, Visible-Ops)
Agile Practices (standup, backlog) | | DevOps Practices (ci/cd)
Agile Tools (jira) | | DevOps (jenkins, ansibles, aws, docker)

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

## devopscon berlin 2018

### best practices
- events not metrics
- dashboards can be misleading (dashborad = artefact of past failure)
- sampling not aggregation
- instrumentation
- events tell storeis (high cardinalities e.g. (high) UUID vs (low) gender )

## sustain devops culture
- devops is a people problems
- intentions is to support decision making
- theory of constraints
- "walk in my shoes" (watch others do their job, solve specific problem)
- cultural mindset (people will adapt, clear expectation and boundaries)
- invocation vs predictability (be clear about time-slots and coutcome)
- growing people like plants (environment, balanced fertilizer)
- "society of emergency docktors" => short attention spanc
- appreciate solved problems not just corssing of checklist !
  - e.g. dba-queryy -> stupid dev, bt 30% load reduced !
- __Autonomy FOLLOWS alignment__ <= company goal !!
- judgement in retrospective is easy
- devops -> collaboration -> look outside your box -> empathy

## monitoring the uknown
- statsd, openTSDB
- `Root Cause Analysis` 
  - method of problem solving used for identifying the root-cause of faults or problems
  - a factor is considered a root-cause if removal fromt he problem-fault-sequence prevents the final undesirable event from reocouring

## keynote
- "consistency bias"
- devops is a revolutionary adaptation to adapt to exponensial change
- maxim: Adapt or die
- "lean thinking" silos
- be disruptive or be disrupted
- frequency of innovation

F. Winslow Tylor | W.Edward Deming
--|--
Efficienty Movement | Lean Movement
Power & Fear | Japan after WWII

- "change for change's sake is dangerous" if not "anchored-change"
- control vs adaptation
- hirarchy vs decentralization

## see also

- [[12 factor app]]
- [[gitops]]
- [theagileadmin.com/what-is-devops/](https://theagileadmin.com/what-is-devops/)
- [[kubernetes]]

