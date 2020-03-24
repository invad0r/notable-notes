---
tags: [bash]
title: bash getops
created: '2019-07-30T06:19:49.009Z'
modified: '2020-03-16T18:01:39.254Z'
---

# bash getops

## usage
```sh
while getopts u:d:p:f: option; do
  case "${option}" in
    u)
      USER=${OPTARG}
      ;;
    d)
      DATE=${OPTARG}
      ;;
    p)
      PRODUCT=${OPTARG}
      ;;
    f)
      FORMAT=$OPTARG
      ;;
  esac
done

echo $USER
echo $DATE
echo $PRODUCT
echo $FORMAT
```

## see also
- [[bash while]]
- [[bash case]]
