---
tags: [bash, linux]
title: diff
created: '2019-07-30T06:19:49.036Z'
modified: '2019-07-30T18:53:00.131Z'
---

# diff
```sh
diff -y file1.json file2.json      # -y, --side-by-side

diff --unified file1.json file2.json
```

```sh
diff <(sort <(md5deep -r /$1/) |cut -f1 -d' ') <(sort <(md5deep -r /$2/) |cut -f1 -d' ')

diff -y <(curl -s https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash) <(cat `brew --prefix`/etc/bash_completion.d/git-completion.bash)
```


### dynamic width
```sh
diff -y -W $(tput cols) <(docker service inspect pp-backend_application) <(docker service inspect presseportal-backend_application)
```
[Make diff Use Full Terminal Width in Side-by-Side Mode - Unix & Linux Stack Exchange](https://unix.stackexchange.com/a/9303)
