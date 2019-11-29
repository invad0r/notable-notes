---
tags: [linux]
title: parallel
created: '2019-07-30T06:19:49.203Z'
modified: '2019-10-22T04:00:17.615Z'
---

# parallel

> GNU Parallel is a replacement for xargs and for loops. It can also split a file or a stream into blocks and pass those to commands running in parallel

## usage
```sh
parallel --jobs 200% gzip ::: *.html        # Compress all *.html files in parallel – 2 jobs per CPU thread in parallel

parallel lame {} -o {.}.mp3 ::: *.wav       # Convert all *.wav to *.mp3 using lame – 1 job per CPU thread in parallel (default)

cat bigfile | parallel --pipe grep foobar   # Chop bigfile into 1MB blocks and grep for the string foobar


parallel -j2 ./script.sh -- $(echo 1 2 3)

parallel --eta -j8 ./script.sh {} :::: ./foo.csv

# --bar


tail -n +266300 ./OTSDE/shortener_OTSDE_YESPPYESPM_OK.txt.csv | parallel --eta ./parallel_check-short-links.sh {}


ls *.json | parallel "ls -lh {}"
```

## input sources
```sh
parallel echo ::: cmd line input source

cat input_from_stdin | parallel echo

parallel echo ::: multiple input sources ::: with valuesparallel -a input_from_file echo

parallel echo :::: input_from_file

parallel echo :::: input_from_file ::: and command line
```

## see also
- [[xargs]]
- https://www.gnu.org/software/parallel/parallel_cheat.pdf
- http://www.shakthimaan.com/posts/2014/11/27/gnu-parallel/news.html
