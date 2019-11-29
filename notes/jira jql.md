---
title: jira jql
created: '2019-09-19T06:12:55.493Z'
modified: '2019-09-19T14:51:18.429Z'
---

# jira jql

> JQL stands for JIRA Query Language (not to be confused with Java Query Language)

## usage

```
project = CB and status not in ("Done", "Accepted", "Merged", "Finished") and text ~ "nexus"


and status not in ("Done", "Accepted", "Merged", "Finished") 


project = CB AND text ~ "elastic" ORDER BY id DESC
```

## see also
- https://confluence.atlassian.com/jiracore/blog/2015/07/search-jira-like-a-boss-with-jql
