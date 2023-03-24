---
tags: [linux, macos]
title: numfmt
created: '2021-10-19T11:54:38.435Z'
modified: '2023-03-22T09:49:49.262Z'
---

# numfmt

> convert numbers from/to human-readable strings

## install

```sh
brew install coreutils
```

## flag

```sh
-d, --delimiter=DELIM     # use DELIM instead of whitespace for field delimiter
    --field=FIELDS        # replace the numbers in these input fields (default=1); see FIELDS below
    --format=FORMAT       # use printf style floating-point FORMAT; see FORMAT below for details
    --from=UNIT           # auto-scale input numbers to UNITs; default is 'none'; see UNIT below
    --from-unit=N         # specify the input unit size (instead of the default 1)
    --grouping            # use locale-defined grouping of digits, e.g. 1,000,000 (which means it has no effect in the C/POSIX locale)
    --header[=N]          # print (without converting) the first N header lines; N defaults to 1 if not specified
    --invalid=MODE        # failure mode for invalid numbers: MODE can be: abort (default), fail, warn, ignore
    --padding=N           # pad the output to N characters; positive N will right-align; negative N will left-align; 
                          #  padding is ignored if the output is wider than N; the default is to automatically pad if a whitespace is found
    --round=METHOD        # use METHOD for rounding when scaling; METHOD can be: up, down, from-zero (default), towards-zero, nearest
    --suffix=SUFFIX       # add SUFFIX to output numbers, and accept optional SUFFIX in input numbers
    --to=UNIT             # auto-scale output numbers to UNITs; see UNIT below
    --to-unit=N           # the output unit size (instead of the default 1)
-z, --zero-terminated     # line delimiter is NUL, not newline

    --debug               # print warnings about invalid input
    --help                # display help and exit
    --version             # output version information and exit
```

### units

```sh
none    # no auto-scaling is done; suffixes will trigger an error

auto    # accept optional single/two letter suffix:
        # 1K = 1000, 1Ki = 1024, 1M = 1000000, 1Mi = 1048576,

si      # accept optional single letter suffix:
        # 1K = 1000, 1M = 1000000, ...

iec     # accept optional single letter suffix:
        # 1K = 1024, 1M = 1048576, ...

iec-i   # accept optional two-letter suffix:
        # 1Ki = 1024, 1Mi = 1048576, ...
```

### usage

```sh
numfmt --to=si 1000               # "1.0K"

numfmt --to=iec 2048              # "2.0K"

numfmt --to=iec-i 4096            # "4.0Ki"

echo "1K" | numfmt --from=si      # "1000"

echo "1K" | numfmt --from=iec     # "1024"

echo "7931556Ki" | numfmt --from=iec-i --to=iec

df -B1 | numfmt --header --field 2-4 --to=si
ls -l  | numfmt --header --field 5   --to=iec
ls -lh | numfmt --header --field 5 --from=iec --padding=10
ls -lh | numfmt --header --field 5 --from=iec --format "%10f"


numfmt --field=2 --from-unit=1024 --to=iec-i --suffix B < /proc/meminfo  | sed 's/ kB//' | head -n4
numfmt --field=2 --from-unit=1024 --to=iec-i --suffix B < <(echo 'MemTotal:       263761228 kB')  |   sed 's/ kB//'
```

## see also

- [[unit]]
- [[coreutils]]
- [[free]]
- [[crane]]
- [gnu.org/coreutils/manual/numfmt](https://www.gnu.org/software/coreutils/manual/html_node/numfmt-invocation.html)
- [pixelbeat.org/docs/numfmt](https://www.pixelbeat.org/docs/numfmt.html)
