---
tags: [Notebooks/todo]
title: todo
created: '2019-07-30T06:19:49.254Z'
modified: '2019-08-18T18:18:39.079Z'
---

# todo

## work
- [ ] traefik tls-terminating ? beta ?
- [ ] kafka cloud blackup solutions ?
- [x] deploy new swarm
  - [x] set `mtu:9000` for new swarm-nodes
  - [x] install github.com/ContainX/docker-volume-netshare/
  - [x] mesure with `dd` before and after `mtu: 9000`
  - [ ] vsphere host11-16 seperate network
    - [ ] create dedicated nfs-iface `mtu:9000`
- [ ] `kibana` monitoring on `elastic-monitor-client-1` broken ?
- [ ] `graylog-ui` NAT not working ? deploy in host-mode ?
- [x] upgrade `cadvisor` container
- [ ] compose list for service which could use `ldap`
  - [x] nexus, gitlab, graylog
  - [ ] vault, grafana, prometheus
- gitlab 
  - [ ] backup to `s3` ?
  - [ ] test release and release-notes with `infrastructure`
  - [ ] tls with ip-san
  - [x] gitlab disk space
    - https://docs.gitlab.com/ee/administration/job_traces.html
    - `/mnt/sda1/var/lib/docker/volumes/gitlab_data/_data/shared/artifacts`
    - `2019_01_04/*/*/job.log`
- prometheus
  - [ ] alert for down scrapper !
  - [ ] prometheus/alerting `sda1` and `sda2` ..further partitions missing in alerting ?

## learn
- [ ] adapter pattern
- [ ] factory pattern
- java
  - [ ] java 11 features
  - [ ] keyword: `final`, `static`
  - [ ] elif aggregator
  - [ ] stream processing
  - [ ] look at company `StreamProcessor.java`
- kafka 
  - [ ] log sequence correct order across brokers
  - [ ] transactional, exactly-once, at-least-once
- [ ] event-sourcing (how is deletino handled ?)
