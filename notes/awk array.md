---
tags: [awk]
title: awk array
created: '2020-01-03T07:43:52.878Z'
modified: '2020-01-06T08:04:22.018Z'
---

# awk array

## usage
```sh
awk '{array[$5] += $4}END{
  for(var in array){ 
    printf("%s: %s GB\n",var, array[var]/1024/1024/1024)
  } 
}'

awk '{
  node[1]+=$3;
  node[2]+=$4;
  node[3]+=$5;
  node[4]+=$6;
  }END{ 
    for(i in node){
      printf("elastic-monitor-1-data-%s %s GB\n",i, node[i]/1024)
      } 
}'
```

## see also
- [[awk]]
- [[awk variable]]
- [[awk function]]
