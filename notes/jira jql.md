---
tags: [Notebooks]
title: jira jql
created: '2019-09-19T06:12:55.493Z'
modified: '2023-03-27T07:50:40.585Z'
---

# jira jql

> `jql` - `jira query language` (not `java query language`)

## usage

```
project = CB and status not in ("Done", "Accepted", "Merged", "Finished") and text ~ "nexus"


and status not in ("Done", "Accepted", "Merged", "Finished") 


project = CB AND text ~ "elastic" ORDER BY id DESC
```

## see also

- [confluence.atlassian.com/blog/search-jira-like-a-boss-with-jql](https://confluence.atlassian.com/jiracore/blog/2015/07/search-jira-like-a-boss-with-jql)
