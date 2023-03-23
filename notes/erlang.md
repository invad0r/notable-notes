---
tags: [erlang]
title: erlang
created: '2019-07-30T06:19:49.150Z'
modified: '2023-03-22T09:12:36.612Z'
---

# erlang

> `Erlang is based originally on Prolog, a logic programming language`

> the shell evaluates expressions
> function definitions are not expressions they are forms
> erl-file defnies forms not expressions

> Erlang has two levels of grammar: forms and expressions.
> Erlang shell is line-oriented and expression-oriented

## usage

```sh
erlang

# get version
erl -eval '{ok, Version} = file:read_file(filename:join([code:root_dir(), "releases", erlang:system_info(otp_release), "OTP_VERSION"])), io:fwrite(Version), halt().'
```

## shell

```erlang
help().       -- shell internal commands

f().          -- forget all variable bindings

Foo = 123.    -- Variable always start with uppercase
```

## see also

- [[haskell]]
- [defining-erlang-functions-in-the-shell](https://stackoverflow.com/questions/2065990/defining-erlang-functions-in-the-shell)
- [http://ulf.wiger.net/weblog/2007/11/20/extending-the-erlang-shell-part-1/](http://ulf.wiger.net/weblog/2007/11/20/extending-the-erlang-shell-part-1/)
