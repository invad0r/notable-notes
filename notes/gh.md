---
tags: [linux, macos]
title: gh
created: '2020-11-20T23:44:36.008Z'
modified: '2023-03-23T10:15:21.157Z'
---

# gh

> github cli

## install

```sh
brew install gh
```

## env

```sh
GH_TOKEN, GITHUB_TOKEN            # an authentication token for github.com API requests. Setting this avoids being prompted to authenticate and takes precedence over previously stored credentials (in order of precedence)
GH_ENTERPRISE_TOKEN               # an authentication token for API requests to GitHub Enterprise
GITHUB_ENTERPRISE_TOKEN           # (in order of precedence)
GH_REPO                           # specify the GitHub repository in the "[HOST/]OWNER/REPO" format for commands that otherwise operate on a local repository
GH_HOST                           # specify the GitHub hostname for commands that would otherwise assume the "github.com" host when not in a context of an existing repository
GH_EDITOR                         # the editor tool to use for authoring text
GIT_EDITOR,VISUAL,EDITOR          # (in order of precedence)
BROWSER                           # web browser to use
DEBUG                             # set to any value to enable verbose output to standard error. Include values "api" or "oauth" to print detailed information about HTTP requests or authentication flow
GH_PAGER, PAGER                   # a terminal paging program to send standard output to, e.g. "less" (in order of precedence)
GLAMOUR_STYLE                     # the style to use for rendering Markdown. See https /# /github.com/charmbracelet/glamour#styles
NO_COLOR                          # set to any value to avoid printing ANSI escape sequences for color output
CLICOLOR                          # set to "0" to disable printing ANSI colors in output
CLICOLOR_FORCE                    # set to a value other than "0" to keep ANSI colors in output even when the output is piped
GH_NO_UPDATE_NOTIFIER             # set to any value to disable update notifications. By default, gh checks for new releases once every 24 hours and displays an upgrade notice on standard error if a newer version was found
GH_CONFIG_DIR, XDG_CONFIG_HOME    # directory where gh will store configuration files (in order of precedence)
XDG_STATE_HOME                    # directory where gh will store state files
XDG_DATA_HOME                     # directory where gh will store data files
```

## usage

```sh
gh help environment                       # list supported environment variables

gh repo list [OWNER|ORG] --limit 1000

gh repo create REPOSITORY

gh repo view --web



gh pr view --web

gh pr list --all

gh pr create \
  --base "$(git name-rev $(git rev-parse @{-1}) --name-only)" \
  --title "$(git rev-parse --abbrev-ref HEAD)" --body ""


gh api repos/{owner}/{repo}/releases --jq '.[] | .url, .tag_name'
```

## see also

- [[glab]]
- [[git]]
- [[api github]]
- [github.com/cli/cli](https://github.com/cli/cli)
