---
tags: [linux, moreutils]
title: parallel
created: '2019-07-30T06:19:49.203Z'
modified: '2021-10-06T12:15:00.569Z'
---

# parallel

> gnu parallel is a replacement for xargs and for loops. It can also split a file or a stream into blocks and pass those to commands running in parallel

## install

`brew install parallel`

## usage

```sh
parallel --jobs 200% gzip ::: *.html        # Compress all *.html files in parallel – 2 jobs per CPU thread in parallel

parallel lame {} -o {.}.mp3 ::: *.wav       # Convert all *.wav to *.mp3 using lame – 1 job per CPU thread in parallel (default)

cat bigfile | parallel --pipe grep foobar   # Chop bigfile into 1MB blocks and grep for the string foobar

cat FILE.csv | parallel --eta ./parallel_check-short-links.sh {}

parallel -j2 ./script.sh -- $(echo 1 2 3)

parallel --eta -j8 ./script.sh {} :::: ./foo.csv

# --bar


CMD | parallel --j 0 --eta bash compress.sh {}

ls *.json | parallel "ls -lh {}"


# input sources
parallel echo ::: FILE1 FILE2 FILE3

cat INPUT_FILE | parallel echo

parallel echo ::: FILE1 FILE2 FILE3 ::: with valuesparallel -a INPUT_FILE echo

parallel echo :::: INPUT_FILE

parallel echo :::: INPUT_FILE ::: CMD
```

## see also

- [[moreutils]]
- [[xargs]]
- [gnu.org/software/parallel/parallel_cheat.pdf](https://www.gnu.org/software/parallel/parallel_cheat.pdf)
- [shakthimaan.com/.../gnu-parallel/news.html](http://www.shakthimaan.com/posts/2014/11/27/gnu-parallel/news.html)
