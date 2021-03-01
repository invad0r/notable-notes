---
tags: [vcs]
title: git tag
created: '2019-08-19T13:40:55.748Z'
modified: '2021-02-18T08:24:01.297Z'
---

# git tag

## usage
```sh
git tag -l                        # list all tags

git tag TAG_NAME COMMIT_SHA       # Create a tag reference named name for current commit. Add commit sha to tag a specific commit instead of current one. 


git tag -a TAG_NAME COMMIT_SHA    # create a tag object named name for current commit
git tag -a TAG_NAME -m "MESSAGE"  # aka annotated tag

# get tag types
# "lightweight" tag is a name in refs/tags that refers to a commit object
# "annotated"   tag is a name in refs/tags that refers to a tag object
git for-each-ref
git for-each-ref refs/tags
# object-hash             object-type   name in refs/tags that refers to the object
# 902fa933e4aa130338b47b8 commit        refs/tags/v1.0-light
# 1f486472cca96a3a7fbd78b tag           refs/tags/v1.1-annot
# fd3cf147ac63122b919a036 commit        refs/tags/v1.2-light

git tag -d TAG_NAME               # remove a tag from a local repository

git push --tags
```

## see also
- [[git]]
- [stackoverflow.com/how-can-i-tell-if-a-given-git-tag-is-annotated-or-lightweight](https://stackoverflow.com/a/40499437/14523221)
