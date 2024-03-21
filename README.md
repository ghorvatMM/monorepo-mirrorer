# monorepo-mirrorer

Action that mirrors the current repository into a destination monorepo.

Example usage:

```
name: Clone and Push

on:
  workflow_dispatch:  # Trigger manually

env:
  SUBFOLDER_NAME: ${{ vars.NAME }}
  DEST_REPO: ${{ vars.DEST_REPO }}
  IGNORE: ${{ vars.IGNORE }}  
  
jobs:
  push-to-remote:
    runs-on: ubuntu-latest

    steps:
      - uses: ghorvatMM/monorepo-mirrorer@v1
        with:
          name: ${{env.SUBFOLDER_NAME}}
          repository: ${{env.DEST_REPO}}
          token: ${{secrets.GH_PAT}}
          ignore: ${{env.IGNORE}}
          gituser: 'Poject bot'
          gitemail: 'info@company.com'          

```