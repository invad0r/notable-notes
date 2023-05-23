---
tags: [compiler, javascript]
title: coffee
created: '2023-05-13T12:00:15.256Z'
modified: '2023-05-19T12:49:42.109Z'
---

# coffee

> execute scripts, compile `.coffee` files into `.js`, and provide a repl

## install

```sh
npm install --save-dev coffeescript   # locally for a project
npm install --global coffeescript     # globally to execute .coffee files anywhere
```

## option

```sh
-c, --compile 	      # Compile a .coffee script into a .js JavaScript file of the same name
-t, --transpile 	    # pipe compiler’s output through Babel before saving or running the generated js
-m, --map 	          # generate source maps alongside the compiled JavaScript files. Adds sourceMappingURL directives to the JavaScript as well
-M, --inline-map 	    # just like --map, but include the source map directly in the compiled JavaScript files, rather than in a separate file
-i, --interactive 	  # Launch an interactive CoffeeScript session to try short snippets. Identical to calling coffee with no arguments
-o, --output DIR  	  # Write out all compiled JavaScript files into the specified directory. Use in conjunction with --compile or --watch
-w, --watch 	        # Watch files for changes, rerunning the specified command when any file is updated
-p, --print 	        # Instead of writing out the JavaScript as a file, print it directly to stdout
-s, --stdio 	        # Pipe in CoffeeScript to STDIN and get back JavaScript over STDOUT
-l, --literate 	      # parses code as Literate CoffeeScript. You only need to specify this when passing in code directly over stdio, or using some sort of extension-less file name
-e, --eval 	          # compile and print a little snippet of CoffeeScript directly from the command line
-r, --require MODULE  # require() given module before starting the REPL or evaluating the code given with the --eval flag
-b, --bare 	          # compile js without the top-level function safety wrapper
--no-header 	        # suppress header
--nodejs              # forward options directly to node executable, useful options, --debug, --debug-brk, --max-stack-size, and --expose-gc
--ast 	              # generate an abstract syntax tree of nodes of the CoffeeScript. Used for integrating with JavaScript build tools
--tokens 	            # instead of parsing the CoffeeScript, just lex it, and print out the token stream. Used for debugging the compiler
-n, --nodes 	        # instead of compiling the CoffeeScript, just lex and parse it, and print out the parse tree. Used for debugging the compiler
```

## usage

```sh
coffee                                            # start repl

coffee --compile --output lib/ src/               # compile a directory tree of .coffee files in src into a parallel tree of .js files in lib

coffee --watch --compile experimental.coffee      # watch a file for changes, and recompile it every time the file is saved

coffee --join project.js --compile src/*.coffee   # concatenate a list of files into a single script

coffee -bpe "alert i for i in [0..10]"            # print out the compiled JS from a one-liner

coffee -o lib/ -cw src/                           # All together now, watch and recompile an entire project as you work on it

cat src/cake.coffee | coffee -sc

coffee -e "console.log num for num in [10..1]"
```

## see also

- [[javascript]]
- [[coffeescript]]
