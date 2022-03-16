---
title: aws-nuke
created: '2022-02-03T08:04:22.692Z'
modified: '2022-03-04T07:34:57.919Z'
---

# aws-nuke

> remove all resources from an aws account

## install

```sh
wget -c https://github.com/rebuy-de/aws-nuke/releases/download/v2.16.0/aws-nuke-v2.16.0-linux-amd64.tar.gz -O - | sudo tar -xz -C $HOME/bin

docker run --rm -it \
  -v $(pwd)/.aws:/home/aws-nuke/.aws \
  quay.io/rebuy/aws-nuke:v2.16.0 \
  --profile default \
  --config /home/aws-nuke/.aws/nuke-config.yml
```

## config

```sh
cat <<EOF > nuke-config.yaml
regions:
- eu-west-1
- global

account-blocklist:
- "999999999999"      # production

accounts:
  "000000000000": {} # aws-nuke-example
  "111100001111":
    filters:
      IAMUser:
      - "admin"
      IAMUserPolicyAttachment:
      - "admin -> AdministratorAccess"
      IAMUserAccessKey:
      - "admin -> AKSDAFRETERSDF"
      - "admin -> AFGDSGRTEWSFEY"

resource-types:
  excludes:
  - IAMUser # don't nuke IAM users
EOF
```

## flags

```sh
--no-dry-run              # to actually nuke resources
--access-key-id           # access key
--secret-access-key       # secret access key
```

## usage

```sh
aws-nuke resource-types   # list resources

aws-nuke -c config/nuke-config.yml --profile aws-nuke-example
```

## see also

- [[aws]]
- [[localstack]]

