---
tags: [container]
title: crane
created: '2021-10-19T11:44:42.215Z'
modified: '2022-02-10T11:18:57.942Z'
---

# crane

> tool for interacting with remote images and registries

## install

`brew install crane`

## usage

```sh
crane export ubuntu - | tar -tvf - | less         # List files in an image

crane export ubuntu - | tar -Oxf - etc/passwd     # Extract a single file from an image
                                                  # Note: Be sure to remove the leading `/` from the path (not `/etc/passwd`). This behavior will not follow symlinks.

crane append -f <(tar -f - -c some-dir/) -t IMAGE     # Bundle directory contents into an image
                                                      # default: produces an image with one layer containing the directory contents. 
                                                      # Add `-b ${BASE_IMAGE}` to append the layer to a base image instead.

crane mutate IMAGE --entrypoint=some-dir/entrypoint.sh     # make an executable in the appended layer the image's entrypoint.

# because `crane append` emits the full image reference, these calls can even be chained together:
# will bundle `SOME_DIR/` into an image, push it, mutate its entrypoint to `SOME_DIR/entrypoint.sh`, and push that new image by digest
crane mutate $(crane append -f <(tar -f - -c SOME_DIR/) -t IMAGE) --entrypoint=SOME_DIR/entrypoint.sh


diff <(crane config busybox:1.32 | jq) <(crane config busybox:1.33 | jq)        # diff two configs
diff <(crane manifest busybox:1.32 | jq) <(crane manifest busybox:1.33 | jq)    # diff two manifests


crane manifest gcr.io/buildpacks/builder:v1 | jq '.config.size + ([.layers[].size] | add)'                      # get total image size
crane manifest gcr.io/buildpacks/builder:v1 | jq '.config.size + ([.layers[].size] | add)' | numfmt --to=iec    # make human-readable by passing to numfmt


crane digest IMAGE
```

## see also

- [[skopeo]]
- [[coreutils]]
- [[jq]]
- [github.com/google/go-containerregistry/crane/README.md](https://github.com/google/go-containerregistry/blob/main/cmd/crane/README.md)
- [github.com/google/go-containerregistry/crane/recipes.md](https://github.com/google/go-containerregistry/blob/main/cmd/crane/recipes.md)
