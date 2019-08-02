---
tags: [bash]
title: bash getops
created: '2019-07-30T06:19:49.009Z'
modified: '2019-07-30T06:22:29.791Z'
---

# bash getops

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
