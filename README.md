<p align="center">
  <a href="https://github.com/actions/typescript-action/actions"><img alt="typescript-action status" src="https://github.com/actions/typescript-action/workflows/build-test/badge.svg"></a>
</p>

# Github Action to delete comments by username

Delete-comment Action will delete comments from issues/prs by username. You can either 
specify an issue number on which to remove comments or let the action remove all comments
across the repository.

## Sample Manually Triggered Workflow

```yaml
name: delete comments from open-collective-bot
on:
  workflow_dispatch:
jobs:
  delete-comments:
    runs-on: ubuntu-latest
    steps:
      - uses: GetDutchie/github-action-delete-comment@v1.0.0
        with: 
          github_token: ${{ secrets.DUTCHIE_BOT_TOKEN }}
          delete_user_name: pulumi[bot]
          issue_number: ${{ github.event.number }}  # remove comments from the current PR
```
