---
tags: [linux, osx]
title: tar
created: '2019-07-30T06:19:49.251Z'
modified: '2020-01-03T12:28:00.450Z'
---

# tar

> "tape archiver" is used to convert a group for file to an archive

`.tgz` is same as `.tar.gz`/`.tar.gzip`

## usage
```sh
tar cvzf archive.tar.gzip dirname/      # create

  #   -c     create archive
  #   -v     verbose
  #   -z     filter the archive through gzip
  #   -f     archive filename

tar cvfj archive-name.tar.bz2 dirname/
  #   -j    filter the archive through bzip2


tar xvf archive.tar                     # extract / untar
  # -x      extract files from archive


docker export tempconsul | tar -C ./rootfs -xf -
  # -C dir    Changes the working directory in the middle of a command line
  # -f stdin  `-` ist stdin


tar tvf archive.tar                     # listing
  # -t      List archive contents to stdout.

tar ztvf archive.tar.gz    # gzipped file

tar tvf archive.tar.gz 'search-pattern'
tar tvf archive.tar.gz 'path/*/file'



tar -czf - archive | wc -c       # estimating

tar -cjf - archive | wc -c        # estimating


# progress
tar cf - erl_crash.dump -P \
  | pv -s $(( $(du -sk erl_crash.dump | cut -f1) * 1024 )) \
  | gzip > erl_crash.dump.tar.gz

tar cf - "$1" -P | pv -s $(( $(du -sk "$1" | cut -f1) * 1024 )) \
  | gzip > "${1}.tar.gz"
```

## see also
- [[zip]]
- [[zcat]]
- [[nc]]
- [[bash redirects]]
- [manual/tar.html - gnu.org](https://www.gnu.org/software/tar/manual/tar.html)
- [why-would-i-tar-a-single-file - unix.stackexchange.com](https://unix.stackexchange.com/a/277799/193945)
