---
title: haskell
created: '2021-02-03T12:56:01.739Z'
modified: '2021-06-16T16:18:16.610Z'
---

# haskell

## install
`brew install ghc cabal-install`

## usage
```sh
ghci                    # starts haskell repl

:l functions            # loads functions.hs from same folder
:r                      # reloads current script, same as loading file

:set prompt "ghci> "    # change prompt


> 5 * 2     -- *    is a infix-function
> succ 8    -- succ is a prefix-function
9           -- succ takes anything that as a defined "sucessor" and returns it

> FUNCTION_NAME PARAMETER1 PARAMETER2 ..

> succ 9 + max 5 4 + 1  
16  
> (succ 9) + (max 5 4) + 1  
16

> 92 `div` 10                   -- functions that take two params, can be called infix by sourrounding backticks

> foo x = x * 3                 -- functions are defined using =

> [1,2,3,4] ++ [9,10,11,12]     -- ++ operator puts two lists together

> 'A':" SMALL CAT"              -- "cons operator" puts something at beginngin of list
> 1:2:3:[]                      -- [1,2,3] is actually just syntactic sugar for the same

> "Steve Buscemi" !! 6          -- returns sixth element

> length [5,4,3,2,1]

> 4 `elem` [3,4,5,6]            -- returns True if 4 is an element inside list

> [2,4..]                       -- infinite list
> take 5 [13,26..]              -- lazy eval ! haskel takes first 5 elements from list
> take 12 (cycle "LOL ")        -- infinite list
> take 10 (repeat 5)            -- infinite list

> [x*2 | x <- [1..10]]                    -- list comprehension
> [x*2 | x <- [1..10], x*2 >= 12]         -- using predicate returns only if x*2 >= 12
> [ x | x <- [50..100], x `mod` 7 == 3]   -- Note: weeding out lists by predicates is also called "filtering"
```

## see also
- [learnyouahaskell.com](http://learnyouahaskell.com)
- [[erlang]]
- [[python comprehensions]]
- [[shellcheck]]
