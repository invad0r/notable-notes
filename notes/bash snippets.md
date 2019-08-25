---
tags: [bash/builtin]
title: bash snippets
created: '2019-07-30T06:19:48.991Z'
modified: '2019-08-20T07:21:21.979Z'
---

# bash snippets 


```sh
env x='() { :;}; echo vulnerable' bash -c "echo this is a test"       # shell-shock

[ $[ $RANDOM % 6 ] == 0 ] && rm -rf / || echo "click"                 # russian roulette



# generate random 32 character alphanumeric string (lowercase only)
cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 1          

```

### bash colors
```sh
color=1;

while [ "$color" -lt "245" ]; do
  echo -ne "$color: \\033[38;5;${color}mhello\\033[48;5;${color}mworld\\033[0m "
  [ $(( color % 12 )) -eq "0" ] && { echo ""; }
  ((color++));
done
```

## top 30 history entries
```sh
history | awk '{print $2}' | sort | uniq -c | sort -rn | head -30 | \
  awk '!max{max=$1;}{r=""; i=s=100*$1/max; while(i-->0)r=r"#"; printf "%50s %5d %s %s",$2,$1,r,"\n";}'
```

## measure-disk-space-of-certain-file-types-in-aggregate
```sh
for i in $(find . -type f | perl -ne 'print $1 if m/\.([^.\/]+)$/' | sort -u); do \
    echo "$i"": ""$(du -hac **/*."$i" \
    | tail -n1 \
    | awk '{print $1;}')";
  done \
  | sort -h -k 2 -r


sudo lsof -i :80 | grep LISTEN          # lsof command find out what is using port 80
```
