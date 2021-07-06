# sitepreview

![GitHub repo size](https://img.shields.io/github/repo-size/gmt-china/sitepreview)
[![Clean up](https://github.com/gmt-china/sitepreview/actions/workflows/cleanup.yaml/badge.svg)](https://github.com/gmt-china/sitepreview/actions/workflows/cleanup.yaml)

The `gh-pages` branch of this repository hosts the documentation from PRs
of other repositories, so that we can preview the changes in PRs.

## How it works

The [`preview-pr.yml`](https://github.com/gmt-china/GMT_Docs/blob/master/.github/workflows/preview-pr.yml)
workflow is triggered in PRs. It builds and pushes the documentation to the
to the `gh-pages` branch of this repository, and creates/updates a comment
with the preview URL link.

The URL scheme is:

    https://gmt-china.github.io/sitepreview/gmt-china/<repository_name>/<PR_branch_name>

## Cleanup

The [`cleanup.yml`](.github/workflows/cleanup.yaml) workflow runs daily to:

1. Delete the documentation if the corresponding branch was already deleted
2. Generate an index file, which lists preview links for open PRs
3. Squash all commits into one commit to avoid increasing repository size
