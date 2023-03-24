---
tags: [container]
title: gcloud
created: '2019-07-30T06:19:49.144Z'
modified: '2023-03-22T10:09:58.402Z'
---

# gcloud

> manage google cloud platform resources and developer workflow

## install

```sh
brew ?
```

## usage

```sh
gcloud init

gcloud projects list

gcloud projects list --format='value(projectId)'
  --format='value(name)'
  --format='value(project_number)'
  --format='value(project_id)'
  --format='value(project_id)' --filter='project_id ~ principal'
  --format='value(project_id)' --filter='project_id ~ foo'
  --format='value(project_id)' --filter='project_id ~ ^printcipal'
  --format='value(project_id)' --filter='project_id ~ ^print'
  --format='value(project_id)' --filter='project_id ~ ^princ'
  --format='value(project_id)' --filter='project_id ~ ^principal'


gcloud iam service-accounts list --project="$(gcloud projects list --format='value(project_id)')"

gcloud compute instances list --project="$(gcloud projects list --format='value(project_id)')"

gcloud --verbosity=debug compute ssh gke-kubia-default-pool-12345678-12ab


gcloud container clusters list

gcloud container clusters get-credentials [kubia]

ssh -t -i /Users/user/.ssh/google_compute_engine \
  -o CheckHostIP=no \
  -o HostKeyAlias=compute.140709..0101147 \
  -o IdentitiesOnly=yes \
  -o StrictHostKeyChecking=no \
  -o UserKnownHostsFile=/Users/user/.ssh/google_compute_known_hosts \
  USER@HOST
```

## see also

- [[kubectl]]
- [[eksctl]]
- [[aws]]
- [[ssh]]
