---
tags: [lang/awk]
title: awk snippets
created: '2019-08-02T07:17:02.123Z'
modified: '2019-08-02T07:17:50.148Z'
---

# awk snippets

```sh
awk '{if (NR!=1) {print} }'     # skip first line

awk '{print $NF}'               # prints last field

awk '{$1=$2=""; print $0}'      # don't print fields $1 and $2

awk '$3 ~ /^[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}/ {print $1,$3}'  # print where $3 has an IPv4

tar tvf scripts.tar | awk -F/ '{if (NF<4) print }'                          # print only first level of files

awk '(NR%2 && /pattern/) || (!(NR%2) && /anotherpattern/)'                  # (NR%2) even and !(NR%2) uneven

awk 'BEGIN{ FS=";" }{ print $6 }'

awk -F'";"' '{ if (length($6)>31) print length($6),$6 }'

awk '{ if( $1 ~ "swarm" && $3 == "alive") { split($2, arr, ":");  print arr[1]} }'  # split '10.32.23.150:8301'
```

### csv
```sh
awk 'BEGIN {FS=","} ($15 != "") && ($19 == "10mbps SDSL" || $20 == "40mbps SDSL") { print .. }'

awk 'BEGIN{FS=";"; TOTAL=0.00}{ if(NR!=1) {
      gsub(/\./,"");  # remove dot from numbers like 4.000,00
      gsub(/,/,".");  # replace , with . due to locale problems -.-
      TOTAL +=sprintf("%f",$4);
      printf "%s %.2f %.2f\n",$4,$4,TOTAL
    }
  }END{ printf "%.2f\n",TOTAL }'

awk '{ split($1,swm,"."); split($2,svs,"_"); tmp = svs[1]" "services[swm[1]]; services[swm[1]]=tmp; }END{ 
    for (i in services) { 
      n=split(services[i], foo, " ");
      print i, n, services[i] 
    }
  }'
```
