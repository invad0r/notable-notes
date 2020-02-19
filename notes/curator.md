---
tags: [elasticsearch]
title: curator
created: '2019-09-19T08:01:33.456Z'
modified: '2020-02-19T13:22:21.369Z'
---

# curator

> `curator`,`curator_cli` and `es_repo_mgr`

## install
`pip install elasticsearch-curator`

## usage
```sh
~/.curator/.curator.yml     # config

curator [--config CONFIG.YML] [--dry-run] ACTION_FILE.YML
```

## curator_cli
```sh
curator_cli show_indices --filter_list '{"filtertype":"pattern","kind":"prefix","value":"myindex"}'
```

## es_repo_mgr
> snapshot repository manager for Elasticsearch curator
```sh
es_repo_mgr show

es_repo_mgr --config .curator/config.yml create fs --help
es_repo_mgr                              create fs --repository es_snapshot_name --location es_snapshot_path --compression true
es_repo_mgr --config .curator/config.yml create fs --repository filebeat_backup --location /bkp --compression True --skip_repo_fs_check True

es_repo_mgr delete
```

## see also
- [[elasticsearch api]]

