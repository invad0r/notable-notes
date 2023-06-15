---
tags: [erlang, runtime]
title: erlang
created: '2019-07-30T06:19:49.150Z'
modified: '2023-05-25T11:41:57.285Z'
---

# erlang

> based originally on [[prolog]], a logic programming language

## env

```sh
ERL_CRASH_DUMP            # filename of crash dump file. If not set crash dump file will be erl_crash.dump in the current directory
ERL_CRASH_DUMP_NICE       # set nice value for the process, thus lowering its priority, range is 1 through 39 
ERL_CRASH_DUMP_SECONDS    # number of seconds that the emulator will be allowed to spend writing a crash dump
ERL_AFLAGS                # content of this environment variable will be added to the beginning of the command line for erl
```

## option

```sh
-eval EXP      # init flag, makes init evaluate the expression EXP, which coordinates system startup
-noshell       # starts a runtime system with no shell, makes it possible to have the runtime system as a component in a series of Unix pipes
```

## usage

```sh
erlang

# get version
erl -eval \
  '{ok, Version} = file:read_file(filename:join([code:root_dir(), "releases", erlang:system_info(otp_release), "OTP_VERSION"])), io:fwrite(Version), halt().'

erl -eval -noshell -configfd 3 \
  'io:format("~p~n",[application:get_env(kernel, logger_level)]),erlang:halt()' 3< \
  <(echo '[{kernel, [{logger_level, warning}]}].')
```

## repl

- the shell evaluates expressions, function definitions are not expressions they are forms, erl-file defnies forms not expressions
- has two levels of grammar: forms and expressions, shell is line-oriented and expression-oriented

```erlang
help().       -- shell internal commands

f().          -- forget all variable bindings

Foo = 123.    -- Variable always start with uppercase
```

## see also

- [[erlc]]
- [[rabbitmqctl]]
- [[haskell]]
- [erlang.org/doc/man/erl](https://www.erlang.org/doc/man/erl.html)
- [learnyousomeerlang.com/content](https://learnyousomeerlang.com/content)
- [blog.stenmans.org/theBeamBook/](https://blog.stenmans.org/theBeamBook/)
- [defining-erlang-functions-in-the-shell](https://stackoverflow.com/questions/2065990/defining-erlang-functions-in-the-shell)
- [ulf.wiger.net/weblog/2007/11/20/extending-the-erlang-shell-part-1/](http://ulf.wiger.net/weblog/2007/11/20/extending-the-erlang-shell-part-1/)
