---
title: cdk
created: '2022-09-27T06:58:06.755Z'
modified: '2022-11-23T08:36:59.573Z'
---

# cdk

## install

```sh
npm install -g aws-cdk             # install latest version
npm install -g aws-cdk@X.YY.Z      # install specific version
```

## usage

```sh
cdk list          # lists stacks in app
cdk ls

cdk synthesize    # synthesizes and prints the cloudformation template for the specified stack(s)
cdk synth

cdk bootstrap     #	deploys cdk toolkit staging stack

cdk deploy        #	deploys specified stack(s)

cdk destroy       #	destroys specified stack(s)

npm run --silent cdk -- destroy --ci STACK

cdk diff          #	compares specified stack and its dependencies with deployed stack(s) or a local cloudformation template

npm run --silent cdk -- diff --ci -e STACK

cdk metadata      # displays metadata about the specified stack

cdk init          #	creates a new cdk project in the current directory from a specified template

cdk context       #	manages cached context values

cdk docs (doc)    #	opens the cdk api reference in your browser

cdk doctor        #	checks your cdk project for potential problems
```

## see also

- [[aws]]
- [[cfn]]
- [[node]]
- [[npm]]
- [[terraform]]
- [[iac]]
