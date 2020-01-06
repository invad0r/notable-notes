---
tags: [awk]
title: awk variable
created: '2020-01-03T07:41:12.778Z'
modified: '2020-01-06T08:12:12.983Z'
---

# awk variable

## 2 types
- Variable which defines values which can be changed such as field separator `FS` and record separator `RS`
- Variable which can be used for processing and reports such as Number of records, number of fields
```sh
CONVFMT       # conversion format used when converting numbers (default %.6g)

FS            # input field separator; regular expression used to separate fields; also settable by option -Ffs.

NF            # number of fields in the current record

NR            # ordinal number of the current record

FNR           # ordinal number of the current record in the current file
              # Number of Records relative to the current input file / when using two input files => seperate RecordNumbers

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

## see also
- [[awk]]
- [[awk function]]
