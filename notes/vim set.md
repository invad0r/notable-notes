---
tags: [vim]
title: vim set
created: '2019-07-30T06:19:49.261Z'
modified: '2019-07-30T06:24:37.670Z'
---

# vim set


```sh
:se[t]              # show options that differ from their default value
:se[t]              # show all but terminal options

:set[t] number
:set[t] wrap
:set[t] ignorecase

:set[t] list

:set listchars=tab:→\ ,trail:·
:set listchars=tab:>\ ,trail:·,nbsp:.,extends:#
:set listchars=tab:»\ ,trail:·,nbsp:·,extends:›,precedes:‹,space:.


:set hlsearch          # highlight search result (.vimrc)
:noh / :nohlsearch     # temp disable search highlight until next search
```
[Vim documentation: options](http://vimdoc.sourceforge.net/htmldoc/options.html#options)

#### unsetting
```sh
:set nolist

:set list&

:set list!
```
