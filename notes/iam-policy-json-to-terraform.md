---
title: iam-policy-json-to-terraform
created: '2022-03-29T16:06:00.334Z'
modified: '2022-03-29T16:09:58.655Z'
---

# iam-policy-json-to-terraform

## install

```sh
brew install iam-policy-json-to-terraform
```

## flags

```sh
-name string    # name of the policy in generated hcl (default "policy")
-version        # prints the version
```

## usage

```sh
echo '{"Statement":[{"Effect":"Allow","Action":["ec2:Describe*"],"Resource":"*"}]}' | iam-policy-json-to-terraform

iam-policy-json-to-terraform < some-policy.json

# use `terraform console` and then jsonencode() on object which can then be copy-paste-piped
```

## see also

- [[terraform]]
- [[tfk8s]]
- [[go]]
- [github.com/flosell/iam-policy-json-to-terraform](https://github.com/flosell/iam-policy-json-to-terraform)
