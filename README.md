# github-action-update-theme

Updates hugo theme and synchronizes Forestry frontmatter.

Requires Deno and Hugo. Example:

```yml
name: Theme Update

on:
  repository_dispatch:
    types: theme-released
  push:
    branches:
      - main

jobs:
  theme-released:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - uses: denolib/setup-deno@v2
    - uses: peaceiris/actions-hugo@v2
    - uses: reima-ecom/github-action-update-theme@v1
      with:
        forestry-source: reima-ecom/reima-theme
```