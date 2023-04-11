---
tags: [linux, macos]
title: awk
created: '2019-07-30T06:19:48.989Z'
modified: '2023-03-23T10:13:22.289Z'
---

# awk

> domain-specific-language for text processing, data extraction and reporting
> data-driven scripting language
> name derived from authors surnames: Alfred Aho, Peter Weinberger, and Brian Kernighan

### implementations

- [[nawk]]: `new awk` (evolution of `oawk`), the original unix implementation
- [[mawk]]: a fast implementation that mostly sticks to standard features
- [[gawk]]: the gnu implementation, with many extensions
- [[busybox]]: small, intended for embedded systems, not many features

## option

```sh
-f SCRIPT      # read awk program from file

-F ";"         # field seperator
```

## variables

```sh
# 2 types
# variable which defines values which can be changed such as field separator `FS` and record separator `RS`
# variable which can be used for processing and reports such as Number of records, number of fields

CONVFMT       # conversion format used when converting numbers (default %.6g)
FS            # input field separator; regular expression used to separate fields; also settable by option -Ffs.
NF            # number of fields in the current record
NR            # ordinal number of the current record
FNR           # ordinal number of the current record in the current file
              # Number of Records relative to the current input file / hen using two input files => seperate RecordNumbers

FILENAME      # the name of the current input file
RS            # input record separator (default newline)
OFS           # output field separator (default blank)
ORS           # output record separator (default newline)
OFMT          # output format for numbers (default %.6g)
SUBSEP        # separates multiple subscripts (default 034)
ARGC          # argument count, assignable
ARGV          # argument array, assignable; non-null members are taken as filenames
ENVIRON       # array of environment variables; subscripts are names.
```

## functions

```sh
printf "%10.0f\n" 1.28071e+09                     # print scientific notation as float to stdout

var = fprintf("%s %d %.2f\n", "Testing", 1, 3) }  # assigns its output to a variable, not stdout

split($1,swm,".");                                # split $1 into array swm[] with optional seperator "."

substr("foobar", 2, 3)                            # => "oob"

substr("foobar", 4)                               # => "bar"

length("foo")                                     # => 3

tolower("FOO")                                    # => "foo"

toupper("foo")                                    # => "FOO"

gsub(/"/, "")                                   #"# remove quotes globally
```

## usage

```sh
awk '{$1=$1;print}'   # trim whitespace from STDOUT
                      # works because assigning something to one of the fields, awk rebuilds the whole record
                      # by joining all fields ($1, ..., $NF) with OFS (space by default)
awk '{$1=$1};1'       # shorter
awk '{$1=$1};NF'      # also remove blank lines, NF: only print records for which the Number of Fields is non-zero

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

- [learnxinyminutes.com/docs/awk](https://learnxinyminutes.com/docs/awk/)
- [[sed]]
- [[grep]]
- [[column]]
