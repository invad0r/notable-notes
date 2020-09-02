---
tags: [awk]
title: awk
created: '2019-07-30T06:19:48.989Z'
modified: '2020-09-01T12:44:02.346Z'
---

# awk

> domain-specific-language for text processing, data extraction and reporting
> data-driven scripting language
> name derived from authors surnames: Alfred Aho, Peter Weinberger, and Brian Kernighan

### implementation
- `nawk`   : `new awk` (evolution of `oawk`), the original unix implementation
- `mawk`   : a fast implementation that mostly sticks to standard features
- `gawk`   : the gnu implementation, with many extensions
- `busybox`: small, intended for embedded systems, not many features

## usage
```sh
awk -f        # Read the AWK program source from file

awk -F        # Field Seperator


awk '{if (NR!=1) {print} }'     # skip first line

awk '{print $NF}'               # prints last field

awk '{$1=$2=""; print $0}'      # don't print fields $1 and $2

awk '$3 ~ /^[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}/ {print $1,$3}'  # print where $3 has an IPv4

tar tvf scripts.tar | awk -F/ '{if (NF<4) print }'                          # print only first level of files

awk '(NR%2 && /pattern/) || (!(NR%2) && /anotherpattern/)'                  # (NR%2) even and !(NR%2) uneven

awk 'BEGIN{ FS=";" }{ print $6 }'

awk -F'";"' '{ if (length($6)>31) print length($6),$6 }'

awk '{ if( $1 ~ "swarm" && $3 == "alive") { split($2, arr, ":");  print arr[1]} }'  # split '10.32.23.150:8301'


echo foo.bar.bbaz.com | awk 'BEGIN{FS="."}{print substr($3,2),$1}'


# usage of arrays
awk '{array[$5] += $4}END{ for(var in array){ printf("%s: %s GB\n",var, array[var]/1024/1024/1024) } }'

awk '{ node[1]+=$3; node[2]+=$4; node[3]+=$5; node[4]+=$6; }END{ 
    for(i in node){ printf("elastic-monitor-1-data-%s %s GB\n",i, node[i]/1024) } }'


# matching ipv4 pattern
awk 'BEGIN{ ORS="\n" }{ if ($3 ~ /^[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}/) { print $1} }'

awk 'BEGIN{ NF=NF RS= OFS=+ }{ \
  if ($3 ~ /^[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}/) { \
    gsub(/^[[:space:]]+|[[:space:]]+$/,"",$1); print $1} \
  }'


# reading csv
awk 'BEGIN {FS=","} ($15 != "") && ($19 == "10mbps SDSL" || $20 == "40mbps SDSL") { print .. }'

awk 'BEGIN{FS=";"; TOTAL=0.00}{ if(NR != 1) {
      gsub(/\./,"");  # remove dot from numbers like 4.000,00
      gsub(/,/,".");  # replace , with . due to locale problems -.-
      TOTAL +=sprintf("%f",$4);
      printf "%s %.2f %.2f\n",$4,$4,TOTAL
    }
  }END{ printf "%.2f\n",TOTAL }'

awk '{ 
  split($1,swm,"."); split($2,svs,"_"); tmp = svs[1]" "services[swm[1]]; services[swm[1]]=tmp; }END{ 
    for (i in services) { n=split(services[i], foo, " "); print i, n, services[i] }
  }'

# cursor bounce around the terminal
# Make your cursor bounce around the terminal. The 400000 in the for loop is just a busy delay. Adjust as needed.
yes $COLUMNS $LINES | awk 'BEGIN{x=y=e=f=1}{if(x==$1||!x){e*=-1};if(y==$2||!y){f*=-1};x+=e;y+=f;printf "\033[%s;%sH",y,x;for (a=0;a<400000;a++){}}'
```

## see also
- [[awk variable]]
- [[awk function]]
- [awk - learnxinyminutes.com](https://learnxinyminutes.com/docs/awk/)
