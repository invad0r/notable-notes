---
title: aws securityhub
created: '2020-10-26T08:01:01.001Z'
modified: '2021-02-03T08:21:29.487Z'
---

# aws securityhub

## usage
```sh
aws securityhub get-findings \
  --filters <filter criteria JSON> \
  --sort-criteria <sort criteria> \
  --page-size <findings per page> \
  --max-items <maximum number of results>

aws securityhub get-findings \
  --filter 'SeverityLabel={Value=CRITICAL,Comparison=EQUALS},ComplianceStatus={Value=FAILED,Comparison=EQUALS},ResourceType={Value=AwsS3Bucket,Comparison=EQUALS}' \
  | jq -r '.Findings[].Resources[].Id'

aws securityhub get-findings \
  --filters '{"GeneratorId":[{"Value": "aws-foundational","Comparison":"PREFIX"}],"WorkflowStatus": [{"Value": "NEW","Comparison":"EQUALS"}],"Confidence": [{"Gte": 85}]}' \
  --sort-criteria '{"Field": "LastObservedAt","SortOrder": "desc"}' \
  --page-size 5 --max-items 100
```

## see also
- [[aws]]
