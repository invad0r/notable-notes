---
tags: [iac]
title: cdk
created: '2022-09-27T06:58:06.755Z'
modified: '2023-03-22T09:16:37.554Z'
---

# cdk

> aws cloud development kit

## install

```sh
npm install -g aws-cdk             # install latest version
npm install -g aws-cdk@X.YY.Z      # install specific version
```

## usage

```sh
npm run --silent cdk -- diff       # run cdk via npm

cdk list          # lists stacks in app
cdk ls

cdk synthesize    # synthesizes and prints the cloudformation template for the specified stack(s)
cdk synth

cdk bootstrap                     #	deploys cdk toolkit staging stack

cdk bootstrap --show-template     # render template

cdk bootstrap --trust AWS_ACCOUNT --trust-for-lookup AWS_ACCOUNT \
  --cloudformation-execution-policies 'arn:aws:iam::aws:policy/POLICY' \
  --template cdk_bootstrap_template.yml

cdk deploy        #	deploys specified stack(s)

cdk deploy --ci -e STACK

cdk destroy       #	destroys specified stack(s)

cdk destroy --ci STACK

cdk diff          #	compares specified stack and its dependencies with deployed stack(s) or a local cloudformation template

cdk diff --ci -e STACK

cdk metadata      # displays metadata about the specified stack

cdk metadata -j BaseStack 2>/dev/null | jq '.["/BaseStack/chatbot-slack/Resource"][].type'

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
