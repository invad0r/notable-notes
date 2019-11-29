---
tags: [vim]
title: vim set
created: '2019-07-30T06:19:49.261Z'
modified: '2019-09-05T11:27:56.034Z'
---

# vim set

set options that configure Vim are of three types:
- `boolean`: on or off (`:help 'autochdir'`)
- `number`: an integer value (`:help 'textwidth'`)
- `string`: a string value (`:help 'backspace'`) 

```sh
:help set

:se[t]              # show options that differ from their default value
                    # show all but terminal options

:set number 	    # Turn line numbers on
:set nonumber 	  # Turn line numbers off

:set invnumber    # Toggle line numbers
:set number!

:set number& 	    # Set option to default value
:set number? 	    # Show value of option 
````

option          | short | example             | desc
--              | --    | --                  | --
`shellcmdflag`  |       | `shellcmdflag=-ic`  | to make Vim’s :! shell behave like your command prompt e.g. for aliases
`encoding`      |       | `encoding=utf-8 `   |   
`tabstop`       |       | `tabstop=2`         | 
`filetype`      | `ft`  | `ft=json`           |
`autoindent`    |       |         |   
`pastetoggle`   |       | pastetoggle=<F3> |   
`ignorecase`    |       |         | 
`list`          |       |         | 
`number`        |       |         | 
`wrap`          |       |         | 
`hlsearch`      | `hls` |                             | highlight search result (.vimrc)
`listchars`     | `lcs` | `listchars=tab:→\ ,trail:·` |

## listchars
```vim
:set listchars=tab:→\ ,trail:·
:set listchars=tab:>\ ,trail:·,nbsp:.,extends:#
:set listchars=tab:»\ ,trail:·,nbsp:·,extends:›,precedes:‹,space:.
```

## see also
- [Vim documentation: options](http://vimdoc.sourceforge.net/htmldoc/options.html#options)
- [commands-executed-from-vim-are-not-recognizing-bash .. - stackoverflow.com](https://stackoverflow.com/a/4642855/2087704)
