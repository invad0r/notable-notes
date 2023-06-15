---
tags: [javascript, runtime, rust, typescript]
title: deno
created: '2023-05-19T12:51:29.466Z'
modified: '2023-05-24T08:45:57.081Z'
---

# deno

> "dee-no" - [[javascript]], [[typescript]], and [[wasm]] runtime based on v8, written in [[rust]]

## install

```sh
brew install deno
```

## env

```sh
DENO_AUTH_TOKENS     # semi-colon separated list of bearer tokens and hostnames to use when fetching remote modules from private repositories
DENO_TLS_CA_STORE    # comma-separated list of order dependent certificate stores. Possible values: "system", "mozilla". Defaults to "mozilla".
DENO_CERT            # load certificate authority from PEM encoded file
DENO_DIR             # set the cache directory
DENO_INSTALL_ROOT    # set deno install's output directory (defaults to $HOME/.deno/bin)
DENO_REPL_HISTORY    # set REPL history file path History file is disabled when the value is empty (defaults to $DENO_DIR/deno_history.txt)
DENO_NO_PACKAGE_JSON # disables auto-resolution of package.json
DENO_NO_PROMPT       # set to disable permission prompts on access (alternative to passing --no-prompt on invocation)
DENO_NO_UPDATE_CHECK # set to disable checking if a newer Deno version is available
DENO_V8_FLAGS        # set V8 command line options
DENO_JOBS            # number of parallel workers used for the --parallel flag with the test subcommand. Defaults to number of available CPUs.
HTTP_PROXY           # proxy address for HTTP requests (module downloads, fetch)
HTTPS_PROXY          # proxy address for HTTPS requests (module downloads, fetch)
NPM_CONFIG_REGISTRY  # URL to use for the npm registry.
NO_COLOR             # set to disable color
NO_PROXY             # comma-separated list of hosts which do not use a proxy (module downloads, fetch)
```

## option

```sh
    --unstable      # enable unstable features and APIs
-q, --quiet         # suppress diagnostic output
-h, --help          # print help (see more with '--help')
-V, --version       # print version
```

## usage

```sh
deno                  # starte repl

deno help compile

deno bench            # run benchmarks
deno cache            # cache the dependencies
deno check            # Type-check the dependencies

deno compile          # UNSTABLE: Compile the script into a self contained executable
deno compile -h
deno compile --help

deno completions      # generate shell completions
deno coverage         # print coverage reports
deno doc              # show documentation for a module
deno eval             # eval script
deno fmt              # Format source files
deno init             # initialize a new project
deno info             # show info about cache or info related to source file
deno install          # install script as an executable
deno uninstall        # Uninstall a script previously installed with deno install
deno lsp              # start the language server
deno lint             # Lint source files
deno repl             # read Eval Print Loop

deno run              # run a js or ts script
deno run SCRIPT.ts    # run typescript

deno task             # run a task defined in the configuration file
deno test             # run tests
deno types            # print runtime TypeScript declarations
deno upgrade          # Upgrade deno executable to given version
deno vendor           # Vendor remote modules into a local directory
deno help             # print this message or the help of the given subcommand(s)
```

## repl

```js
_ 	          // yields the last evaluated expression
_error 	      // yields the last thrown error

clear()       // clears the entire terminal screen
close()       // close the current REPL session
```

## see also

- [[node]], [[js]]
- [github.com/denoland/deno](https://github.com/denoland/deno)
