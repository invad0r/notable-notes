---
tags: [javascript]
title: node
created: '2020-02-28T21:20:20.353Z'
modified: '2022-02-01T14:59:56.299Z'
---

# node

> server-side [[javascript]] runtime

## install

`brew install node`

## usage

```sh
# environment variables
NODE_OPTIONS=--max-old-space-size=32768

# flags
# -c, --check   check syntax without executing, exits with error code if script is invalid
# -e, --eval    string Evaluate string as JavaScript.


node --version              # get version

node                        # starts repl

node -e "console.log(1)"    # evaluate string

node -e "var data = require('./FILE'); console.log(JSON.stringify(data, null, 2));" # pretty print json from js-obj
```

## repl

```js

.break    // when in the process of inputting a multi-line expression, enter the .break command (or press Ctrl+C) to abort further input or processing of that expression.
.clear    // resets the REPL context to an empty object and clears any multi-line expression being input.
.exit     // close the I/O stream, causing the REPL to exit.
.help     // show this list of special commands.
.save     // save the current REPL session to a file: > .save ./file/to/save.js
.load     // load a file into the current REPL session. > .load ./file/to/load.js
.editor   // enter editor mode (Ctrl+D to finish, Ctrl+C to cancel)



process.cwd()       // current working directory of the nodejs process

process.env         // print env variables

process.version     // current nodejs version


var data = require('./FILE')   // load a FILE
```
## see also
- [[javascript]]
- [[npm]]
- [[yarn]]
- [[npx]]
- [[nvm]]
- [[mongosh]]
- [nodejs.org/api/process.html](https://nodejs.org/api/process.html)
- [nodejs.org/api/repl.html#repl_commands_and_special_keys](https://nodejs.org/api/repl.html#repl_commands_and_special_keys)
