---
tags: [container, container/k8s]
title: gcloud
created: '2019-07-30T06:19:49.144Z'
modified: '2020-10-29T09:43:13.043Z'
---

# gcloud

> manage google cloud platform resources and developer workflow

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
  -o CheckHostIP=no -o HostKeyAlias=compute.1407099891930101147 \
  -o IdentitiesOnly=yes -o StrictHostKeyChecking=no \
  -o UserKnownHostsFile=/Users/user/.ssh/google_compute_known_hosts \
  user@35.205.96.131
```

## see also
- [[ssh]]
- [[kubectl]]
- [[aws]]
