---
tags: [elasticsearch]
title: curator
created: '2019-09-19T08:01:33.456Z'
modified: '2019-10-08T04:49:01.777Z'
---

# curator

## install
`pip install elasticsearch-curator`

```
curator
curator_cli
es_repo_mgr
```

## config
`~/.curator/.curator.yml`

## usage
```sh
curator [--config CONFIG.YML] [--dry-run] ACTION_FILE.YML

curator_cli show_indices --filter_list '{"filtertype":"pattern","kind":"prefix","value":"myindex"}'
```


## es_repo_mgr
```sh
es_repo_mgr show


es_repo_mgr --config .curator/config.yml create fs --help
es_repo_mgr                              create fs --repository es_snapshot_name --location es_snapshot_path --compression true
es_repo_mgr --config .curator/config.yml create fs --repository filebeat_backup --location /bkp --compression True --skip_repo_fs_check True

es_repo_mgr delete
```


## see also
- [[elasticsearch api cat]]

