---
tags: [container/k8s]
title: kubernetes
created: '2019-08-28T08:08:25.156Z'
modified: '2020-06-23T07:08:06.534Z'
---

# kubernetes

> `k8s` = kuberntes (`k` + `numbers of letters to` + `s` )
> `i18n` = internationalization
> `l10n` = localization


- `"broken by design"` => "memorize IP ? you crazy ?"
- all containers in pod have same loopback device
- all containers in pod have same IP !!!
- not imperative but declarative
- resource oriented

## pattern -> repeatable solution
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


## see also
- [[devops]]
- [ro14nd-talks/kubernetes-patterns](https://github.com/ro14nd-talks/kubernetes-patterns)
