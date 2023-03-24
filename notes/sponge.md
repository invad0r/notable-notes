---
tags: [linux, macos]
title: sponge
created: '2022-01-21T13:33:13.007Z'
modified: '2023-03-24T08:23:34.451Z'
---

# sponge

> soak up stdin and write to file
> unlike a shell redirect, sponge soaks up all its input before opening the output file. This allows constructing pipelines that read from and write to the same file.

It also creates the output file atomically by renaming a temp file into place, and preserves the permissions of the output file if it already exists.  If the output file is a special file or symlink, the data
will be written to it.

If no output file is specified, sponge outputs to stdout.

## usage

```sh
sed '..' FILE | grep FOO | sponge FILE

cat $KUBECONFIG |\
  yq e '.users.[].user.exec.args += ["--profile", "dev"]' - -- | \
  sed 's/eksworkshop-eksctl./eksworkshop-eksctl-dev./g' | \
  sponge $KUBECONFIG
```

## see also

- [[moreutils]]
- [[bash redirects]]
- [[sed]]
- [[yq]]
- [[tee]]
