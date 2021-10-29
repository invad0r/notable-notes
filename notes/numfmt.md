---
title: numfmt
created: '2021-10-19T11:54:38.435Z'
modified: '2021-10-19T11:58:04.513Z'
---

# numfmt

> convert numbers from/to human-readable strings

## install

## usage

```sh
numfmt --to=si 1000             # "1.0K"

numfmt --to=iec 2048            # "2.0K"

numfmt --to=iec-i 4096          # "4.0Ki"

echo 1K | numfmt --from=si      # "1000"

echo 1K | numfmt --from=iec     # "1024"

df -B1 | numfmt --header --field 2-4 --to=si
ls -l  | numfmt --header --field 5 --to=iec
ls -lh | numfmt --header --field 5 --from=iec --padding=10
ls -lh | numfmt --header --field 5 --from=iec --format %10f
```

## see also

- [[coreutils]]
- [[crane]]
- [www.gnu.org/software/coreutils/manual/numfmt-invocation.html](https://www.gnu.org/software/coreutils/manual/html_node/numfmt-invocation.html)
