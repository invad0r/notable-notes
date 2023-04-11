---
tags: [javascript]
title: tsc
created: '2022-12-02T14:15:06.277Z'
modified: '2023-03-22T10:43:25.146Z'
---

# tsc

## install

```sh
npm install typescript
```

## option

```sh
-h, --help            # Print this message
-w, --watch           # Watch input files
      --all           # Show all compiler options
-v, --version         # Print the compiler's version
      --init          # Initializes a TypeScript project and creates a tsconfig.json file
-p, --project         # Compile the project given the path to its configuration file, or to a folder with a 'tsconfig.json'
-b, --build           # Build one or more projects and their dependencies, if out of date
    --showConfig      # Print the final configuration instead of building
```

## usage

```sh
tsc                               # compiles current project

tsc app.ts util.ts                # compiles specified files with default compiler options ignoring tsconfig.json

tsc -b                            # build a composite project in working directory

tsc --init                        # creates a tsconfig.json with the recommended settings in the working directory

tsc -p ./path/to/tsconfig.json    # compiles the TypeScript project located at the specified path.

tsc --help --all                  # an expanded version of this information, showing all possible compiler options

tsc --noEmit
tsc --target esnext               # compiles the current project, with additional settings
```

## see also

- [[npm]]
- [[npx]]
