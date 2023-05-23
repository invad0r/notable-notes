---
tags: [c, javascript, runtime]
title: js
created: '2023-05-13T11:31:48.624Z'
modified: '2023-05-23T06:55:42.141Z'
---

# js

> [[spidermonkey]] shell provides a cli to javascript-c engine

## install

```sh
brew install spidermonkey
```

## option

```sh
-f --file=PATH              # File path to run, parsing file contents as UTF-8
-u --utf16-file=PATH        # File path to run, inflating the file's UTF-8 contents to UTF-16 and then parsing that
-m --module=PATH            # Module path to run
-e --execute=CODE           # Inline code to run
-i --shell                  # Enter prompt after running code
-c --compileonly            # Only compile, don't run (syntax checking mode)
-w --warnings               # Emit warnings
-W --nowarnings             # Don't emit warnings
-D --dump-bytecode          # Dump bytecode with exec count for all scripts
-b --print-timing           # Print sub-ms runtime for each file that's run
...
```

## usage

```sh
js SCRIPT.js

js OPTS [[SCRIPT] SCRIPT_ARGS*]
```

## console

```sh

>js help()

>js os.getenv("HOME")

js> load("FILE.js")

js> (function() {
  for (let prop in this) {
    console.log(prop + ': ' + global[prop]);
  }
})()

js> for (let prop in globalThis) {
  console.log(prop + ': ' + globalThis[prop]);
}
```

## see also

- [[javascript]]
- [[node]], [[deno]], [[bun]]
- [spidermonkey.dev/](https://spidermonkey.dev/)
- [udn.realityripple.com/docs/Mozilla/Projects/SpiderMonkey/Introduction_to_the_JavaScript_shell](https://udn.realityripple.com/docs/Mozilla/Projects/SpiderMonkey/Introduction_to_the_JavaScript_shell)
- [udn.realityripple.com/docs/Mozilla/Projects/SpiderMonkey/Hacking_Tips](https://udn.realityripple.com/docs/Mozilla/Projects/SpiderMonkey/Hacking_Tips)
