---
title: op
created: '2021-02-01T08:18:52.088Z'
modified: '2022-12-05T14:44:32.723Z'
---

# op

> 1password cli provides commands to manage and administer a 1password account

## usage

```sh
op signin FOO.1password.eu USER_MAIL

eval $(op signin edithcare)


op list vaults
op list items
op list items --vault VAULT                     # e.g. "Private"

op list templates | jq '.[].name'               # get categories

op list items --tags TAG | op get item - | jq '.details.fields[] | .value'

op get item ITEM_ID

op get totps ITEM_ID                            # get one-time code

op get template "Login" > login_template.json

```

## create

```sh
--generate-password[=recipe]      # give the item a randomly generated password
--tags TAGS                       # add one or more tags (comma-separated) to the item
--template FILE                   # specify the filepath to read an item template from
--title TITLE                     # set the item's title
--url URL                         # set the URL associated with the item
--vault VAULT                     # save the item in this vault
```

```sh
op create item CATEGORIE --template FILE
```

## see also

- [1password.com/downloads/command-line/](https://1password.com/downloads/command-line/)
- [support.1password.com/command-line-getting-started/](https://support.1password.com/command-line-getting-started/)
- [[xkcdpass]]
- [[jq]]
- [[aws]]
