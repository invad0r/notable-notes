---
tags: [bash/builtin]
title: bash complete
created: '2019-07-30T06:19:48.994Z'
modified: '2019-08-20T07:21:21.949Z'
---

# bash complete

```sh
complete -W "word1 word2 .." command    # -W wordlist provide a list of words for completion


complete -A directory dothis           # only directory names



_dothis_completions() {
  COMPREPLY+=("now")                   # array variable used to store the completions        
  COMPREPLY+=("tomorrow")
  COMPREPLY+=("never")
}

complete -F _dothis_completions dothis    # -F flag defining function that will provide the completions
```
[Creating a bash completion script](https://iridakos.com/tutorials/2018/03/01/bash-programmable-completion-tutorial.html)
